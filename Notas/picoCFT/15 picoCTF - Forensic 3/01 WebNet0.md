# WebNet0

# Descripción

 We found this packet capture and key. Recover the flag.
# Solución

- Entrar a wireshark
- Seleccionar el paquete capturado
- Entrar a Preferencias
	- Protocolos
	- TLS
	- Poner la llave
	- Filtrar los datos
		- picoCTF


```  
picoCTF{nongshim.shrimp.crackers}
```


```  
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet0]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2
    61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67    ag: picoCTF{nong
    73 68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63    shim.shrimp.crac
    6b 65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c    kers}..Content-L
Cleaned 3 remaining connection(s) from connection pool
--
    67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73    g: picoCTF{nongs
    68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63 6b    him.shrimp.crack
    65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c 65    ers}..Content-Le
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet0]
└─$ 

```



picoCTF{nongshim.shrimp.crackers}
# Notas adicionales

Comandos usados:
- ssldump


# Referencias

