# MacroHard WeakEdge

# Descripción

I've hidden a flag in this file. Can you find it? Forensics_is_fun.pptm

# Solución
- Descomprimir el paquete zip
- Buscar el archivo hidden en slideMasters
- Decodificar de base 64

```  
picoCTF{D1d_u_kn0w_ppts_r_z1p5}  
```


```  
└─$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " " | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}      
```

# Notas adicionales

Comandos usados:
- unzip
- code .      
- echo
- tr -d " " | base64 -d
# Referencias

