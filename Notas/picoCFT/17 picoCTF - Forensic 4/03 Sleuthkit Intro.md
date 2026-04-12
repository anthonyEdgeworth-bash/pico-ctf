# Sleuthkit Intro

# Descripción

Download the disk image and use mmls on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory. Download disk image Access checker program: nc saturn.picoctf.net 63252
# Solución

```  
picoCTF{mm15_f7w!}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic041/SleuthkitIntro]
└─$ gzip -d disk.img.gz 
                          
┌──(kali㉿kali)-[~/Downloads/Forensic041/SleuthkitIntro]
└─$ mmls -V
The Sleuth Kit ver 4.14.0
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/SleuthkitIntro]
└─$ mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/SleuthkitIntro]
└─$ nc saturn.picoctf.net 63252 
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}
                                                       
```


# Notas adicionales

## Comandos usados

- gzip -d 
	- Comandos usado para descomprimir archivos en formato .img.gz 
- mmls
	- Sirve para ver la tabla de direcciones en memoria de una imagen iso

# Referencias

https://www.youtube.com/watch?v=NrwL5YnC4Gk