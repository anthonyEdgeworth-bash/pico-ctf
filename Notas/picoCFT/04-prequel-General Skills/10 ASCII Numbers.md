# ASCII Numbers

# Descripción

Description
Convert the following string of ASCII numbers into a readable string: 0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x35 0x63 0x31 0x31 0x5f 0x6e 0x30 0x5f 0x71 0x75 0x33 0x35 0x37 0x31 0x30 0x6e 0x35 0x5f 0x31 0x6c 0x6c 0x5f 0x74 0x33 0x31 0x31 0x5f 0x79 0x33 0x5f 0x6e 0x30 0x5f 0x6c 0x31 0x33 0x35 0x5f 0x34 0x34 0x35 0x64 0x34 0x31 0x38 0x30 0x7d 

# Solución

```  
picoCTF{45c11_n0_qu35710n5_1ll_t311_y3_n0_l135_445d4180}
```

```  
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/ASCII-Numbers]
└─$ sed 's/0x//g' number.txt 
70 69 63 6f 43 54 46 7b 34 35 63 31 31 5f 6e 30 5f 71 75 33 35 37 31 30 6e 35 5f 31 6c 6c 5f 74 33 31 31 5f 79 33 5f 6e 30 5f 6c 31 33 35 5f 34 34 35 64 34 31 38 30 7d 
                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/ASCII-Numbers]
└─$ nvim converter.py
                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/ASCII-Numbers]
└─$ nvim converter.py
                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/ASCII-Numbers]
└─$ python3 converter.py 
picoCTF{45c11_n0_qu35710n5_1ll_t311_y3_n0_l135_445d4180}
                                                                   
```


# Notas adicionales

En Kali Linux se usa Dash, cambia las instrucciones de uso en comparación a bash

- sed 's/0x//g' archivo.txt
	- El comando elimina el caracte 0x

python ya tiene la función de convertir:

```  
hex_input_messy = "48 65 6c 6c 6f 0x20 57 6f 72 6c 64"
# Remove spaces and '0x'
cleaned_hex = hex_input_messy.replace(" ", "").replace("0x", "")

bytes_object = bytes.fromhex(cleaned_hex)
ascii_output = bytes_object.decode("ASCII")

print(ascii_output)
# Output: Hello World

```

# Referencias

