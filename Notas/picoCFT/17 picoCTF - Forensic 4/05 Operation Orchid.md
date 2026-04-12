# Operation Orchid

# Descripción

Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.

    Download compressed disk image

# Solución

```  
picoCTF{h4un71ng_p457_1d02081e}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ gzip -d disk.flag.img.gz 
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ fls -o 411648 disk.flag.img
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ icat -i raw -o 411648 disk.flag.img 1875
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword12
shred -u flag.txt
ls -al
halt
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ icat -o 411648  disk.flag.img 1782
Salted__S�+%���+�O��k�ђ(A����c��
                                @]ԣ
L�ޢȤ7� ���؎$�'%                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ icat -o 411648  disk.flag.img 1782 > flag.txt.enc
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepas
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40378722AF7F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ cat flag.txt
picoCTF{h4un71ng_p457_1d02081e}    
```


# Notas adicionales

## Comandos usados

- gzip -d 
	- Sirve para descomprimir archivos .img.gz
- mmls
	- Sirve para enlistar las particiones de la imagen 
- fls -o 411648
	- Sirve para enlistar los datos que hay dentro de cierta sección
- icat -i raw -o 411648
	- Sirve para ver el contenido dentro del inodo 1875 en bruto
- icat -o 411648
	- Muestra el contenido tal cuál del inodo
- icat -o 411648 disk.flag.img 1782 > flag.txt.enc
	- Guarda el contenido actual en un archivo
- openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
	- Desencripta el archivo


# Referencias

