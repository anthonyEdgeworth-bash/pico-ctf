# chrono

# Descripción

How to automate tasks to run at intervals on linux servers? Use ssh to connect to this server:

Server: saturn.picoctf.net
Port: 53001
Username: picoplayer 
Password: kZx-HVJKu8

# Solución

```  
picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}
```


```  
picoplayer@challenge:~$ cd ../..
picoplayer@challenge:/$ ls
bin        dev   lib    libx32  opt   run   sys  var
boot       etc   lib32  media   proc  sbin  tmp
challenge  home  lib64  mnt     root  srv   usr
picoplayer@challenge:/$ cd etc/
picoplayer@challenge:/etc$ cat crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}
picoplayer@challenge:/etc$ 

```



# Notas adicionales

- **El Demonio `cron`:** Es un proceso que corre en segundo plano y revisa cada minuto si hay tareas pendientes por ejecutar según la hora o fecha.
    
- **Sintaxis de Crontab:** Es vital entender cómo se definen los intervalos. Se usa un formato de 5 estrellas (o valores): `m h dom mon dow user command`
    
    - `m`: Minutos (0-59)
        
    - `h`: Hora (0-23)
        
    - `dom`: Día del mes (1-31)
        
    - `mon`: Mes (1-12)
        
    - `dow`: Día de la semana (0-6)


# Referencias

[# PicoCTF Walkthru](https://www.youtube.com/watch?v=lvfC9sLqYQ4&t=259s)