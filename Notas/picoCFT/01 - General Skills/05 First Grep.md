# First Grep

# Descripción
Can you find the flag in the file? This would be really tedious to look through manually, something tells me there is a better way.The flag is in this [file](https://challenge-files.picoctf.net/c_fickle_tempest/92807684f3e52665caaf90d69e1e661f990b8731b2f8005e18631be23ff991bb/file).

# Solución
Para la solución de este problema es un conjunto de comandos y la utilización de las Wilcards de unix 

```  
picoCTF{l3arn_th3_r0p35}
```


```  
 @antho  cat file | grep -a -o "picoCTF{.*}"
picoCTF{grep_is_good_to_find_things_eb80073D}

```

# Notas adicionales

Son conocimientos un poco más avanzados de linux, pero realmente las Wilcards sería bueno darles un repaso para saber como usarlas
# Referencias

[0uski.medium.com](https://0uski.medium.com/picoctf-first-grep-d0fa515a5a65)
[How To Use Unix Wildcards](https://www.warp.dev/terminus/linux-wildcards)

