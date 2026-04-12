# RED

# Descripción

RED, RED, RED, RED Download the image: red.png
# Solución

```  
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic04/RED]
└─$ strings red.png 
IHDR
tEXtPoem
Crimson heart, vibrant and bold,
Hearts flutter at your sight.
Evenings glow softly red,
Cherries burst with sweet life.
Kisses linger with your warmth.
Love deep as merlot.
Scarlet leaves falling softly,
Bold in every stroke.x
IDATx
IEND
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic04/RED]
└─$ exiftool red.png        
ExifTool Version Number         : 13.50
File Name                       : red.png
Directory                       : .
File Size                       : 796 bytes
File Modification Date/Time     : 2025:03:05 22:34:15-05:00
File Access Date/Time           : 2026:04:11 23:08:01-04:00
File Inode Change Date/Time     : 2026:04:11 23:07:55-04:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 128
Image Height                    : 128
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Poem                            : Crimson heart, vibrant and bold,.Hearts flutter at your sight..Evenings glow softly red,.Cherries burst with sweet life..Kisses linger with your warmth..Love deep as merlot..Scarlet leaves falling softly,.Bold in every stroke.
Image Size                      : 128x128
Megapixels                      : 0.016
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic04/RED]
└─$ sudo su                           
[sudo] password for kali: 
┌──(root㉿kali)-[/home/kali/Downloads/Forensic04/RED]
└─# zsteg -s l red.png 
meta Poem           .. text: "Crimson heart, vibrant and bold,\nHearts flutter at your sight.\nEvenings glow softly red,\nCherries burst with sweet life.\nKisses linger with your warmth.\nLove deep as merlot.\nScarlet leaves falling softly,\nBold in every stroke."                                        
chunk:0:IHDR        .. file: Adobe Photoshop Color swatch, version 0, 128 colors; 1st RGB space (0), w 0x80, x 0x806, y 0, z 0; 2nd HSB space (1), w 0x100, x 0, y 0xff01, z 0xff                                                   
b1,rgba,lsb,xy      .. text: "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="                 
b1,rgba,msb,xy      .. file: OpenPGP Public Key
b2,g,lsb,xy         .. text: "ET@UETPETUUT@TUUTD@PDUDDDPE"
b2,rgb,lsb,xy       .. file: OpenPGP Secret Key
b2,bgr,msb,xy       .. file: OpenPGP Public Key
b2,rgba,lsb,xy      .. file: OpenPGP Secret Key
b2,rgba,msb,xy      .. text: "CIkiiiII"
b2,abgr,lsb,xy      .. file: OpenPGP Secret Key
b2,abgr,msb,xy      .. text: "caciiiiicCK"
b3,rgba,msb,xy      .. text: "#~`#vr#7r#7b#"
b3,abgr,msb,xy      .. text: "7r#7r#7r"
b4,b,lsb,xy         .. file: 0421 Alliant compact executable not stripped
                                                                            
┌──(root㉿kali)-[/home/kali/Downloads/Forensic04/RED]
└─# zsteg --lsb  red.png
meta Poem           .. text: "Crimson heart, vibrant and bold,\nHearts flutter at your sight.\nEvenings glow softly red,\nCherries burst with sweet life.\nKisses linger with your warmth.\nLove deep as merlot.\nScarlet leaves falling softly,\nBold in every stroke."                                        
chunk:0:IHDR        .. file: Adobe Photoshop Color swatch, version 0, 128 colors; 1st RGB space (0), w 0x80, x 0x806, y 0, z 0; 2nd HSB space (1), w 0x100, x 0, y 0xff01, z 0xff                                                   
b1,rgba,lsb,xy      .. text: "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="                 
b2,g,lsb,xy         .. text: "ET@UETPETUUT@TUUTD@PDUDDDPE"
b2,rgb,lsb,xy       .. file: OpenPGP Secret Key
b2,rgba,lsb,xy      .. file: OpenPGP Secret Key
b2,abgr,lsb,xy      .. file: OpenPGP Secret Key
b4,b,lsb,xy         .. file: 0421 Alliant compact executable not stripped
                                                                            
┌──(root㉿kali)-[/home/kali/Downloads/Forensic04/RED]
└─# zsteg --lsb --channel rgba  red.png
b1,rgba,lsb,xy      .. text: "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="                 
b2,rgba,lsb,xy      .. file: OpenPGP Secret Key

┌──(root㉿kali)-[/home/kali/Downloads/Forensic04/RED]
└─# echo "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==" | base64 -d
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}                                                                            
┌──(root㉿kali)-[/home/kali/Downloads/Forensic04/RED]
└─# 

```


# Notas adicionales

## Comandos usados
 
- zteg
	- Sirve para visualizar los meta-datos
- exiftool
	- Sirve para ver los meta-datos
- base64 -d
	- Sirve para decodificar un mensaje que este en base 64


# Referencias

https://www.youtube.com/watch?v=tbJwWVW6wk8