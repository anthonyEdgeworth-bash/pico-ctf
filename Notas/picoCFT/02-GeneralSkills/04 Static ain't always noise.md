# Static ain't always noise

# Descripción

Can you look at the data in this binary? The bash script might help! static, ltdis.sh

# Solución


```  
picoCTF{d15a5m_t34s3r_20335e41}
```


```  
┌──(kali㉿kali)-[~/Downloads/04]
└─$ chmod +x ltdis.sh 
                                               
┌──(kali㉿kali)-[~/Downloads/04]
└─$ ./ltdis.sh 
Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
                                               
┌──(kali㉿kali)-[~/Downloads/04]
└─$ ./ltdis.sh static 
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
                                               
┌──(kali㉿kali)-[~/Downloads/04]
└─$ ls
ltdis.sh  static.ltdis.strings.txt
static    static.ltdis.x86_64.txt
                                               
┌──(kali㉿kali)-[~/Downloads/04]
└─$ cat static.ltdis.strings.txt |grep pico

   3020 picoCTF{d15a5m_t34s3r_20335e41}
                                               
┌──(kali㉿kali)-[~/Downloads/04]
└─$                            
                                               
┌──(kali㉿kali)-[~/Downloads/04]
└─$ strings static | grep pico
picoCTF{d15a5m_t34s3r_20335e41}
                                 

```




# Notas adicionales

Hay herramientas para hacer el proceso de desamblado, no hay  necesidad de hacerlo a mano 
# Referencias

