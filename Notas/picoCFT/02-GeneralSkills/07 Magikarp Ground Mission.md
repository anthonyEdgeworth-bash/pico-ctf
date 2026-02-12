# Magikarp Ground Mission

# Descripción

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin.

Additional details will be available after launching your challenge instance.
# Solución


```  
picoCTF{xxsh_0ut_0f_//4t3r_0b24fc4f}
```


```  
──(kali㉿kali)-[~]
└─$ ssh ctf-player@wily-courier.picoctf.net -p 49536   

ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ clear
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ld
-bash: ld: command not found
ctf-player@pico-chall$ ls
2of3.flag.txt  dev                       lib    opt   sbin  usr
bin            etc                       lib64  proc  srv   var
boot           home                      media  root  sys
challenge      instructions-to-3of3.txt  mnt    run   tmp
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_//4t3r_
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ~
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt 
0b24fc4f}ctf-player@pico-chall$ Connection to wily-courier.picoctf.net closed by remote host.
Connection to wily-courier.picoctf.net closed.

```

# Notas adicionales

Tal vez haya un modo más rápido para navegar entre carpetas, hay que investigar+

# Referencias





