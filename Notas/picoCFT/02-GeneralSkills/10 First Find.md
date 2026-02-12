# First Find

# Descripción
Unzip this archive and find the file named 'uber-secret.txt'

# Solución

```  
picoCTF{f1nd_15_f457_ab443fd1}
```

```  
┌──(kali㉿kali)-[~/Downloads/10]
└─$ ls
files  files.zip
                                                             
┌──(kali㉿kali)-[~/Downloads/10]
└─$ find  -name uber*
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
                                                             
┌──(kali㉿kali)-[~/Downloads/10]
└─$ cd ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt

cd: not a directory: ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
                                                             
┌──(kali㉿kali)-[~/Downloads/10]
└─$ cat ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt

picoCTF{f1nd_15_f457_ab443fd1}
                                                             
┌──(kali㉿kali)-[~/Downloads/10]
└─$ 

```

# Notas adicionales

Creó que son los comando más importantes, find y locate 
# Referencias





