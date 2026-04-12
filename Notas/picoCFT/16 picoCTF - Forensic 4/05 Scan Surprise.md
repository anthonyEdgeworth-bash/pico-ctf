# Scan Surprise

# Descripción

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead? You can download the challenge files here:

    challenge.zip

The same files are accessible via SSH here: ssh -p 64577 ctf-player@atlas.picoctf.net Using the password 1ad5be0d. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
# Solución

```  
picoCTF{p33k_@_b00_b5ce2572}
```

## Pasos para llegar a la solución

```  
ctf-player@challenge:~/drop-in$ zbarimg flag.png 
Connection Error (Failed to connect to socket /var/run/dbus/system_bus_socket: No such file or directory)
Connection Null
QR-Code:picoCTF{p33k_@_b00_b5ce2572}
scanned 1 barcode symbols from 1 images in 0.01 seconds

ctf-player@challenge:~/drop-in$ 

```


# Notas adicionales

- zbarimg
	- Sirve para escanear, detectar y decodificar códigos de barras y códigos QR directamente desde archivos de imagen


## Comandos usados

# Referencias


https://www.youtube.com/watch?v=ubnU0Han6eg
