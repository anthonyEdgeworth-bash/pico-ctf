# Special

# Descripción


Description
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM) Start your instance to see connection details. ssh -p 58233 ctf-player@saturn.picoctf.net The password is fd7746b4.


# Solución


```  
picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}
```

```  
Special$ ${parameter=cat < blargh/flag.txt}
${parameter=cat < blargh/flag.txt} 
cat: '<': No such file or directory
picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}
```
# Notas adicionales

**La sintaxis ``` ${parameter='command_here'} ```se utiliza para la expansión de parámetros en scripts de shell. Asigna un valor predeterminado a la variable parámetro si aún no está establecida. 
# Referencias

 [# Pico CTF (Special)](https://josephkimiri.github.io/posts/Special/)