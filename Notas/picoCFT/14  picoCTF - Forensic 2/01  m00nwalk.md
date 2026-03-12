# m00nwalk

# Descripción

 Decode this message from the moon.
# Solución

```  
picoCTF{beep_boop_im_in_space}
```


```  
┌──(kali㉿kali)-[~/Downloads/Forensic02/m00nwalk]
└─$ sstv -d message.wav -o flag.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [##########################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic02/m00nwalk]
└─$ ls
flag.png  message.wav
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic02/m00nwalk]
└─$ open flag.png 
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic02/m00nwalk]
└─$ 

```

# Notas adicionales

- sstv: Comando para hacer la conversión de un audio a imagen

# Referencias

 
 
 
 

