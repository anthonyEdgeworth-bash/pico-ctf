# Webnet1

# Descripción

 We found this packet capture and key. Recover the flag.
# Solución


- Entrar a wireshark
- Seleccionar el paquete capturado
- Entrar a Preferencias
	- Protocolos
	- TLS
	- Poner la llave
- Seleccionar el paquete 47 con la imagen
- Usar strings para ver la información de la imagen

```  
picoCTF{honey.roasted.peanuts}
```

```  
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet1]
└─$ strings vulture.jpg | grep pico 
picoCTF{honey.roasted.peanuts}
                             
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet1]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2
    61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73    ag: picoCTF{this
    2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61    .is.not.your.fla
    67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74    g.anymore}..Cont
--
    67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e    g: picoCTF{this.
    69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67    is.not.your.flag
    2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65    .anymore}..Conte
--
    Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
    Keep-Alive: timeout=5, max=99
    Connection: Keep-Alive
--
    00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b    ........picoCTF{
    68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65    honey.roasted.pe
    61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f    anuts}......ICC_
Cleaned 4 remaining connection(s) from connection pool
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet1]
└─$ 

     
```


# Notas adicionales

Comandos usados: 
- strings
- ssldump
# Referencias

