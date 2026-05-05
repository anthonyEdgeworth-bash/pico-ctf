# basic-mod1

# Descripción

We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message here. Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})
# Solución

```  
picoCTF{R0UND_N_R0UND_79C18FB3}
```

## Código para llegar a la solución

```  

datos = open ('message.txt').read().split()

print(datos)
flag = ""

for n in datos:
    c = int(n) % 37
    if c >= 0 and c <= 25:
        s =chr(c+65)

    elif c >= 26 and c <= 35:
        s = chr(c+22)

    else:
        s = '_'
    flag += s



print(f"picoCTF{{{flag}}}")

```


# Notas adicionales

## Comandos usados

# Referencias

https://youtu.be/t3vRV-j0mF0
