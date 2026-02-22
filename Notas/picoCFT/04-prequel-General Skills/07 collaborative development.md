# collaborative development

# Descripción

My team has been working very hard on new features for our flag printing program! I wonder how they'll work together? You can download the challenge files here:

    challenge.zip
# Solución

```  
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_798f9981} 
```

```  
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ python3 flag.py  
Printing the flag...
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ nvim flag.py    
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ git log flag.py 
commit 5e4b2dae1868abb644627483c78a683286dfe67c (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ git log                                                     
commit 5e4b2dae1868abb644627483c78a683286dfe67c (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$  git reflog
5e4b2da (HEAD -> main) HEAD@{0}: checkout: moving from feature/part-3 to main
12c2ae8 (feature/part-3) HEAD@{1}: commit: add part 3
5e4b2da (HEAD -> main) HEAD@{2}: checkout: moving from main to feature/part-3
5e4b2da (HEAD -> main) HEAD@{3}: checkout: moving from feature/part-2 to main
74989a4 (feature/part-2) HEAD@{4}: commit: add part 2
5e4b2da (HEAD -> main) HEAD@{5}: checkout: moving from main to feature/part-2
5e4b2da (HEAD -> main) HEAD@{6}: checkout: moving from feature/part-1 to main
300cff1 (feature/part-1) HEAD@{7}: commit: add part 1
5e4b2da (HEAD -> main) HEAD@{8}: checkout: moving from main to feature/part-1
5e4b2da (HEAD -> main) HEAD@{9}: commit (initial): init flag printer
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ git branch -a
  feature/part-1
  feature/part-2
  feature/part-3
* main
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ git checkout feature/part-1                                 
Switched to branch 'feature/part-1'
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Feb 21 20:13 .
drwxrwxr-x 3 kali kali 4096 Feb 21 20:08 ..
-rw-rw-r-- 1 kali kali   64 Feb 21 20:13 flag.py
drwxr-xr-x 8 kali kali 4096 Feb 21 20:13 .git
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ python3 flag.py
Printing the flag...
picoCTF{t3@mw0rk_                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ cat flag.py    
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ git branch -a              
* feature/part-1
  feature/part-2
  feature/part-3
  main
                                                                                                                                
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ git checkout feature/part-2 

Switched to branch 'feature/part-2'
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ ls -la                               
total 16
drwxr-xr-x 3 kali kali 4096 Feb 21 20:15 .
drwxrwxr-x 3 kali kali 4096 Feb 21 20:08 ..
-rw-rw-r-- 1 kali kali   64 Feb 21 20:15 flag.py
drwxr-xr-x 8 kali kali 4096 Feb 21 20:15 .git
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ python3 flag.py 
Printing the flag...
m@k3s_th3_dr3@m_                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ ls    
flag.py
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ git branch -a                        
  feature/part-1
* feature/part-2
  feature/part-3
  main
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ git checkout feature/part-3

Switched to branch 'feature/part-3'
                                                                                                        
┌──(kali㉿kali)-[~/Downloads/GeneralSkillsPrequel/collaborative-development/drop-in]
└─$ python3 flag.py 
Printing the flag...
w0rk_798f9981}

```



# Notas adicionales

Nuevos comandos usados:

- └─$ git checkout feature/part-3
	- Es una variante, sirve igualmente para cambiar entre ramas
- git branch -a  
	- Muestra las ramas que hay en local
- git reflog
	- Nos permite ver las ramas y confirmaciones de los git hechos
# Referencias

[medium](https://medium.com/@vgqxjb/collaborative-development-9c1875e7dce2)

