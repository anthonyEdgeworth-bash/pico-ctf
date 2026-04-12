# CanYouSee

# Descripción

How about some hide and seek? Download this file here. 

# Solución

```  
picoCTF{ME74D47A_HIDD3N_3b9209a2}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic04/CanYouSee]
└─$ exiftool ukn_reality.jpg 
ExifTool Version Number         : 13.50
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:03:11 20:05:51-04:00
File Access Date/Time           : 2026:04:11 22:49:54-04:00
File Inode Change Date/Time     : 2026:04:11 22:49:43-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fM2I5MjA5YTJ9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels         

┌──(kali㉿kali)-[~/Downloads/Forensic04/CanYouSee]
└─$ echo cGljb0NURntNRTc0RDQ3QV9ISUREM05fM2I5MjA5YTJ9Cg== | base64 -d
picoCTF{ME74D47A_HIDD3N_3b9209a2}
```


# Notas adicionales

## Comandos usados

- exiftool
	- Sirve para ver los meta datos de una imagen
- base64 -d
	- Sirve para decodificar un mensaje

# Referencias

https://www.youtube.com/watch?v=VTx9DSfEcmM