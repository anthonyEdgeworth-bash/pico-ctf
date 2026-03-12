# So Meta

# Descripción

Find the flag in this [picture](https://challenge-files.picoctf.net/c_fickle_tempest/d534c920bd33d42b413e67d21cacbf7aa232c4823ce29872eca285471558f00a/pico_img.png).
# Solución

```  
picoCTF{s0_m3ta_74af23ab}
```

```  
┌──(kali㉿kali)-[~/Downloads/Forensic/soMeta]
└─$ exiftool pico_img.png 
ExifTool Version Number         : 13.36
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2025:11:21 14:11:04-05:00
File Access Date/Time           : 2026:03:09 14:30:19-04:00
File Inode Change Date/Time     : 2026:03:09 14:29:55-04:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : picoCTF{s0_m3ta_74af23ab}
Image Size                      : 600x600
Megapixels                      : 0.360
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic/soMeta]
└─$ 

```


# Notas adicionales

- exiftool: Herramienta que permite visualizar los meta-datos de un archivo
	- Comando de linux fundamental para los retos Forensic
# Referencias
















