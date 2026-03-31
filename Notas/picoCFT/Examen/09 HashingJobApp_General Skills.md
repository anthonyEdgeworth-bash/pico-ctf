## RETO
 HashingJobApp
## DESCRIPCION
If you want to hash with the best, beat this test!`nc saturn.picoctf.net 51408`
## SOLUCION

```  
picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}
```


Para resolver este desafío, se aplicó un enfoque de línea de comandos en un entorno **Kali Linux**:

1. **Conexión Remota:** Se estableció el enlace con el servidor usando la herramienta **Netcat (`nc`)**.
    
2. **Identificación del Algoritmo:** El servidor especificó el uso de **MD5** (Message Digest Algorithm 5).
    
3. **Cálculo de la Firma Digital:** Se utilizó un "one-liner" de **Python 3** para garantizar que el hash fuera exacto y no incluyera caracteres de control invisibles (como saltos de línea `\n`).
    
    - _Comando utilizado:_ `python3 -c "import hashlib; print(hashlib.md5(b'TEXTO_DEL_RETO').hexdigest())"`
        
4. **Validación:** Se copió el valor hexadecimal de 32 caracteres y se ingresó en la terminal de conexión. Tras completar las solicitudes, el servidor liberó la bandera de éxito.

TERMINAL 1:
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 51408     
Please md5 hash the text between quotes, excluding the quotes: 'hockey'
Answer: 
df0349ce110b69f03b4def8012ae4970
df0349ce110b69f03b4def8012ae4970
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Cleopatra'
Answer: 
f8cbe5a99675fff11ed4d83fc16e2071
f8cbe5a99675fff11ed4d83fc16e2071
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Joan of Arc'
Answer: 
19ba425a542946fcf13228d9ddd53139
19ba425a542946fcf13228d9ddd53139
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}


TERMINAL 2:
┌──(kali㉿kali)-[~]
└─$ python3 -c "import hashlib; print(hashlib.md5(b'hockey').hexdigest())"
df0349ce110b69f03b4def8012ae4970
                                                                                 
┌──(kali㉿kali)-[~]
└─$ 
                                                                                 
┌──(kali㉿kali)-[~]
└─$ python3 -c "import hashlib; print(hashlib.md5(b'Cleopatra').hexdigest())"
f8cbe5a99675fff11ed4d83fc16e2071
                                                                                 
┌──(kali㉿kali)-[~]
└─$ python3 -c "import hashlib; print(hashlib.md5(b'Joan of Arc').hexdigest())"
19ba425a542946fcf13228d9ddd53139

## NOTAS ADICIONALES
Durante la ejecución, se identificaron los siguientes puntos críticos:

- **Problemas de Buffer de Entrada:** Se detectó que al usar comandos como `echo` sin el parámetro `-n`, o al copiar directamente de la terminal, se pueden incluir caracteres de salto de línea. Esto altera el valor del hash final, provocando una respuesta "Incorrect".
    
- **Gestión de Tiempos (Timeout):** El servidor cierra la conexión si la respuesta no se envía en pocos segundos. Esto incentiva el uso de scripts o comandos rápidos en lugar de herramientas web manuales.
    
- **Propiedades del Hash:** Se confirmó que el hashing es una función unidireccional; cualquier cambio mínimo en la entrada (un espacio extra o una mayúscula) produce un **hexdigest** completamente distinto (efecto avalancha).
## REFERENCIAS