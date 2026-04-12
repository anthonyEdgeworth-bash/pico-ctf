# Sleuthkit Apprentice

# Descripción

Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.

    Download compressed disk image

# Solución

```  
picoCTF{by73_5urf3r_2f22df38}

```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic041/SleuthkitApprentice]
└─$ gzip -d disk.flag.img.gz                                 
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/SleuthkitApprentice]
└─$ ls
disk.flag.img
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/SleuthkitApprentice]
└─$ fls -o 2048 disk.flag.img 

┌──(kali㉿kali)-[~/Downloads/Forensic041/SleuthkitApprentice]
└─$ fls -o 360448 -r disk.flag.img

┌──(kali㉿kali)-[~/Downloads/Forensic041/SleuthkitApprentice]
└─$ icat  -o 360448 -r disk.flag.img 2371
picoCTF{by73_5urf3r_2f22df38}
                                
```


# Notas adicionales

## Comandos usados

- fls -o "num" disk.flag.img 
	- Sirve para en-listar los archivos de una partición
- icat  -o 360448 -r
	- Sirve para visualizar un archivo 

# Referencias

