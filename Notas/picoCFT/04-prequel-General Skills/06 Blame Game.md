# Blame Game

# Descripción

Someone's commits seems to be preventing the program from working. Who is it? You can download the challenge files here:

    challenge.zip


# Solución

```  
picoCTF{@sk_th3_1nt3rn_81e716ff}
```

```  
v┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/Blame-Game/drop-in]
└─$ cat message.py 
print("Hello, World!"
                                                                            
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/Blame-Game/drop-in]
└─$ git log
commit 929e3918bed4c8f3432c1f7c7ddfe5b378e177e1 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:17 2024 +0000

    important business work

commit 5611f02bbfed52af8c78eb92ec58a323bebf96da
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:17 2024 +0000

    important business work

commit 455a99a92c0a2cc12675c0cf8cab5762bb7dafae
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:17 2024 +0000

    important business work

commit bd7c2f9c5d330be001284b360ef4702bc7883f9b
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:17 2024 +0000

    important business work

commit f1ee9881c5614b3e01695f1f9b74a8320d8d56fb
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:17 2024 +0000

    important business work

commit f89bbe15744eee2f55f7692e67e5f68687b66d61
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:17 2024 +0000

    important business work

commit 0ae2112e90322e3f5dfc0197251708c68885244f
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:17 2024 +0000

    important business work

                                                                            
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/Blame-Game/drop-in]
└─$ 
                                                                            
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/Blame-Game/drop-in]
└─$ ls
message.py
                                                                            
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/Blame-Game/drop-in]
└─$ git log message.py 
commit 23e9d4ce78b3cea725992a0ce6f5eea0bf0bcdd4
Author: picoCTF{@sk_th3_1nt3rn_81e716ff} <ops@picoctf.com>
Date:   Tue Mar 12 00:07:15 2024 +0000

    optimize file size of prod code

commit 3ce5c692e2f9682a866c59ac1aeae38d35d19771
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:15 2024 +0000

    create top secret project
                                                                            
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/Blame-Game/drop-in]
└─$
```
# Notas adicionales

También puedes aplicar el comando git log sobre los archivos para ver los cambios aplicados por usuario 

# Referencias

[# PicoCTF — Blame Game — Writeup](https://medium.com/@technolifts/picoctf-blame-game-writeup-4849f20116b9)
