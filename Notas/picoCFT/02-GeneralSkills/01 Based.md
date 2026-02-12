# BASED

# Descripción

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?

Additional details will be available after launching your challenge instance.

# Solución

Para la solución de esté problema tuvimos que utilizar un código de python ya  que el acceso al puerto nc esta limitada por 45 segundos

```  
picoCTF{learning_about_converting_values_acdCcfCa}
```


```  
from pwn import remote
import binascii

# --- Funciones de conversión ---

def binary_to_ascii(binary_input):
    try:
        # Elimina espacios y convierte
        binary_cleaned = binary_input.replace(' ', '')
        n = int(binary_cleaned, 2)
        return binascii.unhexlify('%x' % n).decode('utf-8')
    except:
        return None

def octal_to_ascii(octal_input):
    try:
        # CORRECCIÓN AQUÍ:
        # El servidor envía 'o123'. Reemplazamos 'o' por nada.
        clean_input = octal_input.replace('o', '').replace('O', '')
        
        # Separamos por espacios
        octal_values = clean_input.strip().split(' ')
        
        # Convertimos cada número base 8 a caracter
        return ''.join(chr(int(x, 8)) for x in octal_values if x.isdigit())
    except Exception as e:
        return None

def hex_to_ascii(hex_input):
    try:
        # Limpieza extra para Hex por si viene como '0x41 0x42' o '41 42'
        clean_input = hex_input.replace('0x', '').replace(' ', '')
        return bytes.fromhex(clean_input).decode('utf-8')
    except:
        return None

def decode_message(encoded_message):
    # El orden importa. Primero probamos si es Hex/Binario/Octal
    # Probamos Octal primero si tiene 'o', o Binario si son solo 0 y 1
    
    encoded_message = encoded_message.strip()
    
    # Intento 1: Binario (si solo tiene 0, 1 y espacios)
    if all(c in '01 ' for c in encoded_message):
        res = binary_to_ascii(encoded_message)
        if res: return res

    # Intento 2: Octal (si tiene la 'o' famosa o numeros 0-7)
    # Forzamos intento octal
    res = octal_to_ascii(encoded_message)
    if res: return res

    # Intento 3: Hexadecimal
    res = hex_to_ascii(encoded_message)
    if res: return res

    return None

# --- Main ---
def main():
    # Nota: A veces cambia el puerto o host según tu instancia, revisa tu reto
    host = "jupiter.challenges.picoctf.org" 
    port = 29221
    # Si tu reto te dio otra dirección (como fickle-tempest), cámbiala aquí:
    # host = "fickle-tempest.picoctf.net"
    # port = 49845

    print(f"Conectando a {host}:{port}...")
    conn = remote(host, port)

    try:
        while True:
            # Leer datos del servidor
            output = conn.recv(timeout=2).decode('utf-8', errors='ignore')
            
            if not output:
                break
                
            print(output) # Ver lo que pasa

            if "picoCTF{" in output:
                print("\n¡FELICIDADES! BANDERA ENCONTRADA:")
                # A veces la bandera está cortada, leemos el resto
                rest = conn.recvall().decode('utf-8', errors='ignore')
                print(output + rest)
                break

            # Detectar pregunta
            if "Please give the " in output or "Please give me the " in output:
                # Lógica para extraer el texto sucio
                try:
                    # Cortamos desde "Please give..."
                    if "Please give the " in output:
                        fragment = output.split("Please give the ")[1]
                    else:
                        fragment = output.split("Please give me the ")[1]
                    
                    # Cortamos hasta " as a word"
                    encoded = fragment.split(" as a word")[0].strip()
                    
                    print(f"\n[+] Reto detectado: {encoded}")
                    solution = decode_message(encoded)
                    
                    if solution:
                        print(f"[+] Respuesta enviada: {solution}")
                        conn.sendline(solution.encode())
                    else:
                        print("[-] No pude decodificar esto. Revisa el formato.")
                        break
                except IndexError:
                    pass
                    
    except KeyboardInterrupt:
        print("\nSaliendo...")
    finally:
        conn.close()

if __name__ == "__main__":
    main()
```



# Notas adicionales

Para cyber-security hay que saber muy bien python o bash

# Referencias

[medium.com](https://medium.com/@sobatistacyber/picoctf-writeups-based-e4d62df7f529)


