# Picker I

# Descripción

This service can provide you with a random number, but can it do anything else? Connect to the program with netcat: $ nc saturn.picoctf.net 60299 The program's source code can be downloaded here.
# Solución

```  
picoCTF{4_d14m0nd_1n_7h3_r0ugh_ce4b5d5b}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Reversing02/timer]
└─$ nc saturn.picoctf.net 60299
Try entering "getRandomNumber" without the double quotes...
==> win
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x63 0x65 0x34 0x62 0x35 0x64 0x35 0x62 0x7d 
Try entering "getRandomNumber" without the double quotes...
==>                                                           

Decodificar from Hex

picoCTF{4_d14m0nd_1n_7h3_r0ugh_ce4b5d5b}

```


# Notas adicionales

## Comandos usados

# Referencias

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg3MCAweDY5IDB4NjMgMHg2ZiAweDQzIDB4NTQgMHg0NiAweDdiIDB4MzQgMHg1ZiAweDY0IDB4MzEgMHgzNCAweDZkIDB4MzAgMHg2ZSAweDY0IDB4NWYgMHgzMSAweDZlIDB4NWYgMHgzNyAweDY4IDB4MzMgMHg1ZiAweDcyIDB4MzAgMHg3NSAweDY3IDB4NjggMHg1ZiAweDYzIDB4NjUgMHgzNCAweDYyIDB4MzUgMHg2NCAweDM1IDB4NjIgMHg3ZCAK

https://youtu.be/w6-NUCpxyMs