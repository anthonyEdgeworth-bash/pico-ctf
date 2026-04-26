# rsa pop quiz

# Descripción
Class, take your seats! It's PRIME-time for a quiz... nc fickle-tempest.picoctf.net 61120

# Solución

```  
picoCTF{wA8_th4till3aGal..o288ce54c}
```
## Pasos para llegar a la solución

```  
Modificar el código para enlace con tu dirección que te dan en el reto:

from pwn import remote
from sympy import mod_inverse


# ─────────────────────────────────────────────
#  RSA helpers
# ─────────────────────────────────────────────

def calculate_n(p, q):
    return p * q


def calculate_q(p, n):
    return n // p


def totient(p, q):
    return (p - 1) * (q - 1)


def encrypt(plaintext, e, n):
    return pow(plaintext, e, n)


def calculate_d(p, q, e):
    phi_n = (p - 1) * (q - 1)
    return mod_inverse(e, phi_n)


def decrypt(ciphertext, d, n):
    return pow(ciphertext, d, n)


def int_to_ascii(number):
    hex_str = hex(number)[2:]
    if len(hex_str) % 2:
        hex_str = "0" + hex_str
    try:
        return bytes.fromhex(hex_str).decode("utf-8")
    except UnicodeDecodeError:
        return "(no se pudo decodificar como UTF-8)"


# ─────────────────────────────────────────────
#  Parser de parámetros del servidor
# ─────────────────────────────────────────────

def parse_params(message):
    """
    Extrae todos los pares  clave : valor  del mensaje del servidor.
    También captura números sueltos (sin etiqueta) como 'bare_number',
    que el servidor a veces usa como ciphertext real.
    """
    params = {}
    for line in message.splitlines():
        line = line.strip()
        if not line or line.startswith("#"):
            continue
        if ":" in line:
            key, _, value = line.partition(":")
            key   = key.strip().lower().replace(" ", "_")
            value = value.strip()
            if value.lstrip("-").isdigit():
                params[key] = int(value)
        elif line.lstrip("-").isdigit() and len(line) > 15:
            # Número suelto sin etiqueta → probable ciphertext real
            params["bare_number"] = int(line)
    return params


def parse_targets(message):
    """
    Extrae la lista de valores que el servidor pide producir.
    Busca la sección entre '##### PRODUCE THE FOLLOWING ####' y
    'IS THIS POSSIBLE'.
    """
    targets = []
    inside  = False
    for line in message.splitlines():
        line = line.strip()
        if "PRODUCE THE FOLLOWING" in line:
            inside = True
            continue
        if inside:
            if "IS THIS POSSIBLE" in line or line.startswith("#"):
                break
            if line:
                # totient(n) → totient_n  |  cualquier otra cosa: quitar paréntesis
                normalized = line.lower().replace("(n)", "_n").replace("(", "").replace(")", "")
                targets.append(normalized)
    return targets


# ─────────────────────────────────────────────
#  Lógica de decisión
# ─────────────────────────────────────────────

FEASIBLE_COMBOS = {
    # (frozenset de inputs disponibles) : frozenset de outputs producibles
    frozenset({"p", "q"})                   : {"n", "totient_n"},
    frozenset({"p", "n"})                   : {"q", "totient_n"},
    frozenset({"q", "n"})                   : {"p", "totient_n"},
    frozenset({"p", "q", "e"})              : {"d", "n", "totient_n"},
    frozenset({"p", "n", "e"})              : {"d", "totient_n"},
    frozenset({"plaintext", "e", "n"})      : {"ciphertext"},
    frozenset({"p", "ciphertext", "e", "n"}): {"plaintext"},
    frozenset({"q", "ciphertext", "e", "n"}): {"plaintext"},
    frozenset({"p", "q", "ciphertext", "e"}): {"plaintext"},
}


def is_feasible(params, targets):
    available = frozenset(params.keys())
    needed    = set(targets)

    for inputs, outputs in FEASIBLE_COMBOS.items():
        if inputs.issubset(available) and needed.issubset(outputs):
            return True

    # Caso especial: factorizar n para obtener p y q con n pequeño
    if needed == {"q", "p"} and "n" in available and "e" in available:
        n = params["n"]
        if n < 10**20:          # solo si es factorizable rápidamente
            return True

    return False


def compute_answers(params, targets):
    """
    Calcula los valores pedidos a partir de los parámetros disponibles.
    Devuelve un dict { target: value }.
    """
    answers = {}

    # Derivar valores intermedios si es posible
    p = params.get("p")
    q = params.get("q")
    n = params.get("n")
    e = params.get("e")

    if p and q and not n:
        n = calculate_n(p, q)
    if p and n and not q:
        q = calculate_q(p, n)
    if q and n and not p:
        p = calculate_q(q, n)  # same division

    # Factorizar n pequeño si necesitamos p y q
    if ("q" in targets or "p" in targets) and n and not p and not q:
        p = _factor_small_n(n)
        if p:
            q = n // p

    d = None
    if p and q and e:
        d = calculate_d(p, q, e)

    for target in targets:
        if target == "n":
            answers["n"] = n or calculate_n(p, q)

        elif target == "q":
            answers["q"] = q

        elif target == "p":
            answers["p"] = p

        elif target == "totient_n":
            answers["totient_n"] = totient(p, q)

        elif target == "d":
            answers["d"] = d

        elif target == "ciphertext":
            pt = params.get("plaintext")
            answers["ciphertext"] = encrypt(pt, e, n)

        elif target == "plaintext":
            # Si llegó un número suelto, es la continuación de n cortado por TCP
            # El ciphertext correcto es el etiquetado, no el bare_number
            if "bare_number" in params and n:
                n = int(str(n) + str(params["bare_number"]))
                # Recalcular q con el n real completo
                if p and n:
                    q = calculate_q(p, n)
                elif q and n:
                    p = calculate_q(q, n)
                # Recalcular d con el n correcto
                if p and q and e:
                    d = calculate_d(p, q, e)

            ct = params.get("ciphertext")
            if d is None and p and q and e:
                d = calculate_d(p, q, e)
            result = decrypt(ct, d, n)
            answers["plaintext"] = result
            decoded = int_to_ascii(result)
            if decoded.isprintable():
                print(f"\n[FLAG / PLAINTEXT DECODED]: {decoded}\n")

    return answers


def _factor_small_n(n):
    """Factoriza n por fuerza bruta (solo para n pequeños)."""
    if n % 2 == 0:
        return 2
    i = 3
    while i * i <= n:
        if n % i == 0:
            return i
        i += 2
    return None


# ─────────────────────────────────────────────
#  Loop principal
# ─────────────────────────────────────────────

def interact_with_server(host, port):
    print(f"Conectando a {host}:{port}...\n")
    conn = remote(host, port)

    current_params  = {}
    current_targets = []
    challenge_num   = 0

    while True:
        try:
            raw     = conn.recv(timeout=10)
            message = raw.decode("utf-8", errors="replace").strip()
            print(f"[Servidor]:\n{message}\n")

            # ── Actualizar parámetros acumulados del problema actual ──
            new_params  = parse_params(message)
            new_targets = parse_targets(message)

            if new_params:
                current_params.update(new_params)
            if new_targets:
                current_targets = new_targets

            # Limpiar parámetros al inicio de un nuevo problema
            if "NEW PROBLEM" in message:
                current_params  = {}
                current_targets = []
                new_params      = parse_params(message)
                new_targets     = parse_targets(message)
                if new_params:
                    current_params.update(new_params)
                if new_targets:
                    current_targets = new_targets

            # ── Responder Y/N ──────────────────────────────────────────
            if "IS THIS POSSIBLE and FEASIBLE? (Y/N):" in message:
                feasible = is_feasible(current_params, current_targets)
                answer   = "Y" if feasible else "N"
                print(f"[Yo → Y/N]: {answer}  "
                      f"(params={list(current_params.keys())}, "
                      f"targets={current_targets})\n")
                conn.sendline(answer.encode())
                challenge_num += 1

            # ── Responder con valores calculados ──────────────────────
            elif "TIME TO SHOW ME WHAT YOU GOT" in message:
                answers = compute_answers(current_params, current_targets)
                for target in current_targets:
                    # El servidor espera "totient(n):" no "totient_n:"
                    prompt_key = target.replace("totient_n", "totient(n)")
                    value      = answers.get(target)
                    if value is not None:
                        print(f"[Yo → {prompt_key}]: {value}\n")
                        conn.sendline(str(value).encode())
                    else:
                        print(f"[ADVERTENCIA] No pude calcular: {target}")
                        conn.sendline(b"0")

            # ── Detectar cierre ───────────────────────────────────────
            if "ruined" in message.lower() or "flag" in message.lower():
                print("\n[Fin del reto detectado]")
                break

        except EOFError:
            print("\n[Servidor cerró la conexión]")
            break
        except Exception as exc:
            print(f"[Error]: {exc}")
            break

    conn.close()
    print("Conexión cerrada.")


def main():
    host = "fickle-tempest.picoctf.net"
    port = 63528
    interact_with_server(host, port)


if __name__ == "__main__":
    main()
                                                                                                                              
┌──(venv)─(kali㉿kali)-[~/Downloads/crypto02/rsa-pop-quiz]
└─$ 



Ejecutar el código:

┌──(venv)─(kali㉿kali)-[~/Downloads/crypto02/rsa-pop-quiz]
└─$ python3 script.py
Conectando a fickle-tempest.picoctf.net:63528...

[+] Opening connection to fickle-tempest.picoctf.net on port 63528: Done
[Servidor]:
Good morning class! It's me Ms. Adleman-Shamir-Rivest
Today we will be taking a pop quiz, so I hope you studied. Cramming just will not do!
You will need to tell me if each example is possible, given your extensive crypto knowledge.
Inputs and outputs are in decimal. No hex here!
#### NEW PROBLEM ####
q : 60413
p : 76753
##### PRODUCE THE FOLLOWING ####
n
IS THIS POSSIBLE and FEASIBLE? (Y/N):

[Yo → Y/N]: Y  (params=['q', 'p'], targets=['n'])

[Servidor]:
#### TIME TO SHOW ME WHAT YOU GOT! ###

[Yo → n]: 4636878989

[Servidor]:
n:

[Servidor]:
Outstanding move!!!


#### NEW PROBLEM ####
p : 54269
n : 5051846941
##### PRODUCE THE FOLLOWING ####
q
IS THIS POSSIBLE and FEASIBLE? (Y/N):

[Yo → Y/N]: Y  (params=['p', 'n'], targets=['q'])

[Servidor]:
#### TIME TO SHOW ME WHAT YOU GOT! ###

[Yo → q]: 93089

[Servidor]:
q:

[Servidor]:
Outstanding move!!!


#### NEW PROBLEM ####
e : 3
n : 12738162802910546503821920886905393316386362759567480839428456525224226445173031635306683726182522494910808518920409019414034814409330094245825749680913204566832337704700165993198897029795786969124232138869784626202501366135975223827287812326250577148625360887698930625504334325804587329905617936581116392784684334664204309771430814449606147221349888320403451637882447709796221706470239625292297988766493746209684880843111138170600039888112404411310974758532603998608057008811836384597579147244737606088756299939654265086899096359070667266167754944587948695842171915048619846282873769413489072243477764350071787327913
##### PRODUCE THE FOLLOWING ####
q
p
IS THIS POSSIBLE and FEASIBLE? (Y/N):

[Yo → Y/N]: N  (params=['e', 'n'], targets=['q', 'p'])

[Servidor]:
Outstanding move!!!


#### NEW PROBLEM ####

[Servidor]:
q : 66347
p : 12611
##### PRODUCE THE FOLLOWING ####
totient(n)
IS THIS POSSIBLE and FEASIBLE? (Y/N):

[Yo → Y/N]: Y  (params=['q', 'p'], targets=['totient_n'])

[Servidor]:
#### TIME TO SHOW ME WHAT YOU GOT! ###

[Yo → totient(n)]: 836623060

[Servidor]:
totient(n):

[Servidor]:
Outstanding move!!!


#### NEW PROBLEM ####
plaintext : 6357294171489311547190987615544575133581967886499484091352661406414044440475205342882841236357665973431462491355089413710392273380203038793241564304774271529108729717
e : 3
n : 29129463609326322559521123136222078780585451208149138547799121083622333250646678767769126248182207478527881025116332742616201890576280859777513414460842754045651093593251726785499360828237897586278068419875517543013545369871704159718105354690802726645710699029936754265654381929650494383622583174075805797766685192325859982797796060391271817578087472948205626257717479858369754502615173773514087437504532994142632207906501079835037052797306690891600559321673928943158514646572885986881016569647357891598545880304236145548059520898133142087545369179876065657214225826997676844000054327141666320553082128424707948750331
##### PRODUCE THE FOLLOWING ####
ciphertext
IS THIS POSSIBLE and FEASIBLE? (Y/N):

[Yo → Y/N]: Y  (params=['plaintext', 'e', 'n'], targets=['ciphertext'])

[Servidor]:
#### TIME TO SHOW ME WHAT YOU GOT! ###

[Yo → ciphertext]: 256931246631782714357241556582441991993437399854161372646318659020994329843524306570818293602492485385337029697819837182169818816821461486018802894936801257629375428544752970630870631166355711254848465862207765051226282541748174535990314552471546936536330397892907207943448897073772015986097770443616540466471245438117157152783246654401668267323136450122287983612851171545784168132230208726238881861407976917850248110805724300421712827401063963117423718797887144760360749619552577176382615108244813

[Servidor]:
ciphertext:

[Servidor]:
Outstanding move!!!


#### NEW PROBLEM ####
ciphertext : 107524013451079348539944510756143604203925717262185033799328445011792760545528944993719783392542163428637172323512252624567111110666168664743115203791510985709942366609626436995887781674651272233566303814979677507101168587739375699009734588985482369702634499544891509228440194615376339573685285125730286623323
e : 3
n : 27566996291508213932419371385141522859343226560050921196294761870500846140132385080994630946107675330189606021165260590147068785820203600882092467797813519434652632126061353583124063944373336654246386074125394368479677295167494332556053947231141336142392086767742035970752738056297057898704112912616565299451359791548536846025854378347423520104947907334451056339439706623069503088916316369813499705073573777577169392401411708920615574908593784282546154486446779246790294398198854547069593987224578333683144886242572837465834139561122101527973799583927411936200068176539747586449939559180772690007261562703222558103359
##### PRODUCE THE FOLLOWING ####
plaintext
IS THIS POSSIBLE and FEASIBLE? (Y/N):

[Yo → Y/N]: N  (params=['ciphertext', 'e', 'n'], targets=['plaintext'])

[Servidor]:
Outstanding move!!!


#### NEW PROBLEM ####

[Servidor]:
q : 92092076805892533739724722602668675840671093008520241548191914215399824020372076186460768206814914423802230398410980218741906960527104568970225804374404612617736579286959865287226538692911376507934256844456333236362669879347073756238894784951597211105734179388300051579994253565459304743059533646753003894559
p : 97846775312392801037224396977012615848433199640105786119757047098757998273009741128821931277074555731813289423891389911801250326299324018557072727051765547115514791337578758859803890173153277252326496062476389498019821358465433398338364421624871010292162533041884897182597065662521825095949253625730631876637
e : 65537
##### PRODUCE THE FOLLOWING ####
d
IS THIS POSSIBLE and FEASIBLE? (Y/N):

[Yo → Y/N]: Y  (params=['q', 'p', 'e'], targets=['d'])

[Servidor]:
#### TIME TO SHOW ME WHAT YOU GOT! ###
d:

[Yo → d]: 1405046269503207469140791548403639533127416416214210694972085079171787580463776820425965898174272870486015739516125786182821637006600742140682552321645503743280670839819078749092730110549881891271317396450158021688253989767145578723458252769465545504142139663476747479225923933192421405464414574786272963741656223941750084051228611576708609346787101088759062724389874160693008783334605903142528824559223515203978707969795087506678894006628296743079886244349469131831225757926844843554897638786146036869572653204735650843186722732736888918789379054050122205253165705085538743651258400390580971043144644984654914856729

[Servidor]:
Outstanding move!!!


#### NEW PROBLEM ####
p : 153143042272527868798412612417204434156935146874282990942386694020462861918068684561281763577034706600608387699148071015194725533394126069826857182428660427818277378724977554365910231524827258160904493774748749088477328204812171935987088715261127321911849092207070653272176072509933245978935455542420691737433
ciphertext : 8836696262375784993108161925636240116662607135476522090374081619045057605810559227394343474462608504891494303466361335625773211764567686575618904612461618878116159242008480037553147400255199114559199056650927217803896261026186827762120610380973109374234671469455750973186531942502246249646937422341637142393969358837998472548290267598866111250978593602146761308231811133961448757188661718153323658454472693072395989447443940068496611785250069647010235521225914672673606437238664683537313683263433771431121168803620590075321713519807869545356432943768414809161329224207709753818099771475190883917555604287768701016575

[Servidor]:
e : 65537
n : 23952937352643527451379227516428377705004894508566304313177880191662177061878993798938496818120987817049538365206671401938265663712351239785237507341311858383628932183083145614696585411921662992078376103990806989257289472590902167457302888198293135333083734504191910953238278860923153746261500759411620299864395158783509535039259714359526738924736952759753503357614939203434092075676169179112452620687731670534906069845965633455748606649062394293289967059348143206600765820021392608270528856238306849191113241355842396325210132358046616312901337987464473799040762271876389031455051640937681745409057246190498795697239
##### PRODUCE THE FOLLOWING ####
plaintext
IS THIS POSSIBLE and FEASIBLE? (Y/N):

[Yo → Y/N]: Y  (params=['p', 'ciphertext', 'e', 'n'], targets=['plaintext'])

[Servidor]:
#### TIME TO SHOW ME WHAT YOU GOT! ###
plaintext:


[FLAG / PLAINTEXT DECODED]: picoCTF{wA8_th4till3aGal..o288ce54c}

[Yo → plaintext]: 218378661235194013475375491560393839271890611748313869466505982182374965209214385152893

[Servidor]:
Outstanding move!!!


If you convert the last plaintext to a hex number, then ascii, you'll find what you need! ;)


[Servidor cerró la conexión]
[*] Closed connection to fickle-tempest.picoctf.net port 63528
Conexión cerrada.
                  

```


# Notas adicionales

## Comandos usados

# Referencias
