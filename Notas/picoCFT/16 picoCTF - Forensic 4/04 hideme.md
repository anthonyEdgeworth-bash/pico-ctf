# hideme

# Descripción

Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye here.
# Solución

```  
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_96539bea}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic04/hideme]
└─$ binwalk flag.png                                   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2858, uncompressed size: 3015, name: secret/flag.png
42897         0xA791          End of Zip archive, footer length: 22

                                                                    
┌──(kali㉿kali)-[~/Downloads/Forensic04/hideme]
└─$ binwalk -e flag.png 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2858, uncompressed size: 3015, name: secret/flag.png

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                    
┌──(kali㉿kali)-[~/Downloads/Forensic04/hideme]
└─$ ls
flag.png  _flag.png.extracted
                                                                    
┌──(kali㉿kali)-[~/Downloads/Forensic04/hideme]
└─$ cd _flag.png.extracted 
                                                                    
┌──(kali㉿kali)-[~/Downloads/Forensic04/hideme/_flag.png.extracted]
└─$ cd secret             

┌──(kali㉿kali)-[~/…/Forensic04/hideme/_flag.png.extracted/secret]
└─$ eog flag.png

┌──(kali㉿kali)-[~/…/Forensic04/hideme/_flag.png.extracted/secret]
└─$ tesseract flag.png out
Estimating resolution as 110
                                                                    
┌──(kali㉿kali)-[~/…/Forensic04/hideme/_flag.png.extracted/secret]
└─$ cat out.txt 
Picow tT ryridainng_An_image_witnin_@n_imave_Yoossbeay




```


# Notas adicionales

## Comandos usados

binwalk -e
- Sirve para descomprimir objetos dentro de imágenes


# Referencias

