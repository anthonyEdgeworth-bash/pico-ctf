# Picker II

# Descripción

Can you figure out how this program works to get the flag? Connect to the program with netcat: $ nc saturn.picoctf.net 64368 The program's source code can be downloaded here.
# Solución

```  
picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_b924e8e5}
```

## Pasos para llegar a la solución

```  
Ejecutar siguiente comando:

┌──(kali㉿kali)-[~/Downloads/Reversing02/timer]
└─$ nc saturn.picoctf.net 64368
==> print(open('flag.txt','r').read())
picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_b924e8e5}
'NoneType' object is not callable
                                                       
                                                       
```


# Notas adicionales

## Comandos usados

# Referencias

https://youtu.be/Ujl5f4fgRPQ