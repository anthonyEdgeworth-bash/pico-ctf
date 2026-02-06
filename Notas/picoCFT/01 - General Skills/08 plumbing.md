# Plumbing

# Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to fickle-tempest.picoctf.net 51324.

Additional details will be available after launching your challenge instance.

# Solución
Para este reto tenemos que usar la combinación de nc y grep

```  
picoCTF{digital_plumb3r_A01Bc3eC}
```


```  
 jue  5 feb - 21:09  ~/Documentos/Universidad/Optativa_Fundamentos_de_la_Seguridad/retos/General Skills/Obedient Cat   master 4☀ 
 @antho  nc fickle-tempest.picoctf.net 51324 | grep -a -o "picoCTF{.*}"
picoCTF{digital_plumb3r_A01Bc3eC}

```


# Notas adicionales

El comando grep se puede usar en muchos lados

# Referencias

[medium.com](https://medium.com/@sobatistacyber/picoctf-writeups-plumbing-776a8ad6dca5)