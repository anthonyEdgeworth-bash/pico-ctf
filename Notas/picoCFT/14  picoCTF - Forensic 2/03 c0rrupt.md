# c0rrupt

# Descripción

 We found this file. Recover the flag.
# Solución

```  
picoCTF{c0rrupt10n_1847995}
```

```  
└─$ hexeditor flag.png
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Forensic02/c0rrupt]
└─$ pngcheck -v flag.png
File: flag.png (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in flag.png (9 chunks, 96.3% compression).
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Forensic02/c0rrupt]
└─$ open flag.png
                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads/Forensic02/c0rrupt]
└─$ 

```

# Notas adicionales

- hexeditor: Comando en el reto usado, sirve para editar el hexadecimal de un archivo
	- Puedes usarlo para reparar archivos
- pngcheck -v flag.png: Sirve para comprobar la "salud" de una imagen
# Referencias




