# repetitions

# Descripción

Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/477/enc_flag).
# Solución

```  
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
```

```  
┌──(kali㉿kali)-[~/Downloads/08]
└─$ cat enc_flag | base64 -d | base64 -d |base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
                                                             
┌──(kali㉿kali)-[~/Downloads/08]
└─$ 

```
# Notas adicionales

Existe la posibilidad de mandar múltiples veces el mismo comando, esto es nuevo
# Referencias



