# interencdec

# Descripción

Can you get the real meaning from this file. Download the file here. 
# Solución

```  
picoCTF{caesar_d3cr9pt3d_86de32d2}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/crypto01/interencdec]
└─$ cat enc_flag | base64 -d | tr -d "'b" | base64 -d
wpjvJAM{jhlzhy_k3jy9wa3k_86kl32k2}                                                             


- Ir a cyberchef
- Usar el algortimo rot-13
- Rotar 19 veces
```


# Notas adicionales

## Comandos usados

# Referencias

https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,19)&input=d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg2a2wzMmsyfSAgIA&oenc=65001
