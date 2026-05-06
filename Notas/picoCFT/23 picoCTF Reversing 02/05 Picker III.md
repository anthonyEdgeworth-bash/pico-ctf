# Picker III

# Descripción

Can you figure out how this program works to get the flag? Connect to the program with netcat: $ nc saturn.picoctf.net 55234 The program's source code can be downloaded here.

# Solución

```  
picoCTF{7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_a186f9ac}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Reversing02/timer]
└─$ nc saturn.picoctf.net 55234
==> 3
Please enter variable name to write: getRandomNumber
Please enter new value of variable: win
==> 2
Please enter variable name to read: getRandomNumber
<function win at 0x7640f0798dc0>
==> 4
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x37 0x68 0x31 0x35 0x5f 0x31 0x35 0x5f 0x77 0x68 0x34 0x37 0x5f 0x77 0x33 0x5f 0x67 0x33 0x37 0x5f 0x77 0x31 0x37 0x68 0x5f 0x75 0x35 0x33 0x72 0x35 0x5f 0x31 0x6e 0x5f 0x63 0x68 0x34 0x72 0x67 0x33 0x5f 0x61 0x31 0x38 0x36 0x66 0x39 0x61 0x63 0x7d 
==>                                                                                                                    
Convertir el numero From Hex

picoCTF{7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_a186f9ac}
```


# Notas adicionales

## Comandos usados

# Referencias

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg3MCAweDY5IDB4NjMgMHg2ZiAweDQzIDB4NTQgMHg0NiAweDdiIDB4MzcgMHg2OCAweDMxIDB4MzUgMHg1ZiAweDMxIDB4MzUgMHg1ZiAweDc3IDB4NjggMHgzNCAweDM3IDB4NWYgMHg3NyAweDMzIDB4NWYgMHg2NyAweDMzIDB4MzcgMHg1ZiAweDc3IDB4MzEgMHgzNyAweDY4IDB4NWYgMHg3NSAweDM1IDB4MzMgMHg3MiAweDM1IDB4NWYgMHgzMSAweDZlIDB4NWYgMHg2MyAweDY4IDB4MzQgMHg3MiAweDY3IDB4MzMgMHg1ZiAweDYxIDB4MzEgMHgzOCAweDM2IDB4NjYgMHgzOSAweDYxIDB4NjMgMHg3ZCA&oeol=FF

https://youtu.be/j8ZzXUY_O00