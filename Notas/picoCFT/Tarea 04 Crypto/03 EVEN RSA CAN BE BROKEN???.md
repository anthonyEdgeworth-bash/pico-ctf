# EVEN RSA CAN BE BROKEN???

# Descripción

This service provides you an encrypted flag. Can you decrypt it with just N & e? Connect to the program with netcat: $ nc verbal-sleep.picoctf.net 63023 The program's source code can be downloaded here.
# Solución

```  
picoCTF{tw0_1$_pr!m3de643ad5}
```

## Código para llegar a la solución

```  
from Crypto.Util.number import long_to_bytes, inverse

N = 18302785542749080713938026026517400672869164857748380743107808392658901395720479813646188522143912203436194579491953435404125945226688568020648573686232054
e = 65537
ciphertext = 16075813198031056426260042356249374786660966202009030792620565858722947861796077580358746916911195730509997394116342098767097810861237543782596281842869521
p = 9151392771374540356969013013258700336434582428874190371553904196329450697860239906823094261071956101718097289745976717702062972613344284010324286843116027
q = 2

# CORRECCIÓN 1: Sintaxis y Lógica
# Tenías 'p(p-1)', Python cree que intentas llamar a 'p' como una función.
# Además, phi es (p-1)*(q-1)
phi = (p - 1) * (q - 1)

d = inverse(e, phi)
m = pow(ciphertext, d, N)

# CORRECCIÓN 2: Typo en la función
# El import dice 'long_to_bytes' (con S), tú escribiste 'long_to_byte'
flag = long_to_bytes(m).decode()

print("Decrypted flag:", flag)
```


# Notas adicionales

## Comandos usados

# Referencias

