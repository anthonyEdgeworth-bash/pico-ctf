# HideToSee

# Descripción

How about some hide and seek heh? Look at this image here.
# Solución

```  
picoCTF{atbash_crack_92533667}
```

## Pasos para llegar a la solución

```  
Usar el siguiente comando para tener el archivo de texto:

┌──(kali㉿kali)-[~/Downloads/Crypto05/HideToSee]
└─$ steghide extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                            
                                                            
Usar el decodificadior atbash Cipher:
	- krxlXGU{zgyzhs_xizxp_92533667}
	- picoCTF{atbash_crack_92533667}
```


# Notas adicionales

## Comandos usados

- steghide extract -sf atbash.jpg

# Referencias

- https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfOTI1MzM2Njd9
- https://youtu.be/iNcta36CavA
- 
