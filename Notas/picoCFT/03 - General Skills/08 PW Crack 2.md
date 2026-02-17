# PW Crack 2

# Descripción

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.
# Solución


```  
picoCTF{tr45h_51ng1ng_9701e681}
```

```  
┌──(kali㉿kali)-[~/Downloads/GeneraSkills2/pwcrak02]
└─$ cat level2.flag.txt.enc 
D
 Vw1%B@W
        \:ZRWS:ZT
                 T                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneraSkills2/pwcrak02]
└─$ python3 level2.py 
Please enter correct password for flag: hola
That password is incorrect
                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneraSkills2/pwcrak02]
└─$ nvim level2.py                     
                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneraSkills2/pwcrak02]
└─$ python3 level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneraSkills2/pwcrak02]
└─$ 


┌──(kali㉿kali)-[~/Downloads/GeneraSkills2/pwcrak02]
└─$ python3          
Python 3.13.9 (main, Oct 15 2025, 14:56:22) [GCC 15.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) 
>>> '4ec9'
>>> 

```
# Notas adicionales


# Referencias

