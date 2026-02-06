
# Nice netcat...

# Descripción

There is a nice program that you can talk to by using this command in a shell:$ nc wily-courier.picoctf.net 52370, but it doesn't speak English...
# Solución

Para está solución solo usamos un convertidor de ASCII a texto

```  
picoCTF{g00d_k1tty!_n1c3_k1tty!_a94e7}
```

```  
 @antho  nc wily-courier.picoctf.net 52370
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
97 
57 
52 
101 
55 
125 
10 
```

# Notas adicionales

Este problema es parecido a Warm Up, si este tipo de problemas es común tal vez sería mejor un script de python

# Referencias

[medium.com](https://medium.com/@arthDetroja/picoctf-write-up-nice-netcat-a5619128659a)
[Convertidor](https://www.duplichecker.com/ascii-to-text.php)