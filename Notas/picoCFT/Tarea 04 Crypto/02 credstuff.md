# credstuff

# Descripción

We found a leak of a blackmarket website's login credentials. Can you find the password of the user cultiris and successfully decrypt it? Download the leak here. The first user in usernames.txt corresponds to the first password in passwords.txt. The second user corresponds to the second password, and so on.
# Solución

```  
ppicoCTF{C7r1F_54V35_71M3}
```

## Pasos para llegar a la solución

```  
Descomprimir los archivos
- tar -vxf leak.tar        
Buscar en paswords la contraseña:

- ┌──(venv)─(kali㉿kali)-[~/Downloads/Tarea04/credstuff/leak]
└─$ cat passwords.txt | grep {*}
cvpbPGS{P7e1S_54I35_71Z3}
                           
Irnos a:
- https://cryptii.com/pipes/caesar-cipher/
  
Decodificar:

picoCTF{C7r1F_54V35_71M3}


```


# Notas adicionales

## Comandos usados

# Referencias

