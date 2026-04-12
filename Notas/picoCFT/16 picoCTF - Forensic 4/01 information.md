# information

# Descripción

Files can always be changed in a secret way. Can you find the flag? cat.jpg

# Solución

```  
picoCTF{the_m3tadata_1s_modified}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic04]
└─$ exiftool cat.jpg         
ExifTool Version Number         : 13.50
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2025:12:12 14:21:14-05:00
File Access Date/Time           : 2026:04:09 23:08:49-04:00
File Inode Change Date/Time     : 2026:04:09 23:06:25-04:00
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels  


┌──(kali㉿kali)-[~/Downloads/Forensic04]
└─$ echo cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9 | base64 -d
picoCTF{the_m3tadata_1s_modified}     

```



# Notas adicionales

## Comandos usados
 
- exiftool cat.jpg
	- Sirve para ver los meta datos de la imagen
- echo cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9 | base64 -d
	- Sirve para decodificar un mensaje
# Referencias

https://www.youtube.com/watch?v=fteVJetnHbE