# Matryoshka doll

# Descripción

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: dolls.jpg

# Solución

```  
picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}
```


```  
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet1/Matryoshkadoll]
└─$ binwalk dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378933, uncompressed size: 383920, name: base_images/2_c.jpg
651591        0x9F147         End of Zip archive, footer length: 22

                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet1/Matryoshkadoll]
└─$ reset
Erase is control-H (^H).
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet1/Matryoshkadoll]
└─$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378933, uncompressed size: 383920, name: base_images/2_c.jpg
651591        0x9F147         End of Zip archive, footer length: 22

                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet1/Matryoshkadoll]
└─$ binwalk -e dolls.jpg                       

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378933, uncompressed size: 383920, name: base_images/2_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet1/Matryoshkadoll]
└─$ ls
dolls.jpg  _dolls.jpg.extracted
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic03/WebNet1/Matryoshkadoll]
└─$ cd _dolls.jpg.extracted 
                                                                            
┌──(kali㉿kali)-[~/…/Forensic03/WebNet1/Matryoshkadoll/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                            
┌──(kali㉿kali)-[~/…/Forensic03/WebNet1/Matryoshkadoll/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                            
┌──(kali㉿kali)-[~/…/WebNet1/Matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                           
└─$ ls
2_c.jpg
                                                                            
┌──(kali㉿kali)-[~/…/WebNet1/Matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                           
└─$ binwalk 2_c.jpg     

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196025, uncompressed size: 201427, name: base_images/3_c.jpg
383787        0x5DB2B         End of Zip archive, footer length: 22
383898        0x5DB9A         End of Zip archive, footer length: 22

                                                                            
┌──(kali㉿kali)-[~/…/WebNet1/Matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                           
└─$ binwalk -e 2_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196025, uncompressed size: 201427, name: base_images/3_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                            
┌──(kali㉿kali)-[~/…/WebNet1/Matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                           
└─$ ls
2_c.jpg  _2_c.jpg.extracted
                                                                            
┌──(kali㉿kali)-[~/…/WebNet1/Matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                           
└─$ cd _2_c.jpg.extracted  
                                                                            
┌──(kali㉿kali)-[~/…/Matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ ls
2DD3B.zip  base_images
                                                                            
┌──(kali㉿kali)-[~/…/Matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ cd base_images       
                                                                            
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg
                                                                            
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77633, uncompressed size: 79786, name: base_images/4_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                            
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg  _3_c.jpg.extracted
                                                                            
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted 
                                                                            
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ ls
1E2D6.zip  base_images
                                                                            
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ cd base_images       
                                                                            
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                            
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk  4_c.jpg     

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v1.0 to extract, compressed size: 42, uncompressed size: 42, name: flag.txt
79764         0x13794         End of Zip archive, footer length: 22

                                                                            
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk  -e 4_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
79578         0x136DA         Zip archive data, at least v1.0 to extract, compressed size: 42, uncompressed size: 42, name: flag.txt

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                            
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg  _4_c.jpg.extracted
                                                                            
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$  _4_c.jpg.extracted 
                                                                            
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                            
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt  
picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}
                                                                            
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ 

```
# Notas adicionales

Comandos usados: 
- binwalk -e

# Referencias

