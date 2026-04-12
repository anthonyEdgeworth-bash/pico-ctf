# Disk, disk, sleuth!

# Descripción

Use srch_strings from the sleuthkit and some terminal-fu to find a flag in this disk image. dds1-alpine.flag.img.gz
# Solución

```  
picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic041/Diskdisksleuth]
└─$  gzip -d dds1-alpine.flag.img.gz 
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/Diskdisksleuth]
└─$ sudo apt install -y sleuthkit
sleuthkit is already the newest version (4.14.0+dfsg-0kali1).
sleuthkit set to manually installed.
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 500
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/Diskdisksleuth]
└─$ srch_strings dds1-alpine.flag.img | grep pico
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/Diskdisksleuth]
└─$ 

```


# Notas adicionales

## Comandos usados
- gzip -d
	- Sirve para descomprimir archivos de formato .img.gz
- srch_strings
	- Sirve para buscar y mostrar secuencias de caracteres imprimibles

# Referencias

