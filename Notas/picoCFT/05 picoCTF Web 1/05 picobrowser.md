# picobrowser

# Descripción

This website can be rendered only by picobrowser, go and catch the flag! http://fickle-tempest.picoctf.net:57130
# Solución

```  
Flag: picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}
```


```  
┌──(kali㉿kali)-[~/Downloads/picoCTF-Web-1/logon]
└─$ curl -s  http://fickle-tempest.picoctf.net:57130/flag -H "user-Agent: picobrowser" | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}</code></p>
                                                                                                
┌──(kali㉿kali)-[~/Downloads/picoCTF-Web-1/logon]
└─$ 

```

# Notas adicionales

Debe haber herramientas de automatización o más robustas para hacer estas tareas "básicas" de seguridad
# Referencias

