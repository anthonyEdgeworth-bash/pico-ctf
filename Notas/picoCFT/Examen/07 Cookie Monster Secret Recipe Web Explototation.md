# Cookie Monster Secret Recipe

# Descripción

Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe? You can access the Cookie Monster here and good luck
# Solución

```  
picoCTF{c00k1e_m0nster_l0ves_c00kies_78B4C390}
```

## Pasos para resolver el problema

- Ingresar a la web del servidor
- Ingresar claves aleatorias
*(Se nos generará una cookie)*
- Extraemos "value" de la cookie generada
- Usamos el comando
	- echo "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzc4QjRDMzkwfQ%3D%3D" | base64 -d
*(bandera obtenida)*

# Notas adicionales

# Referencias

https://medium.com/@Kamal_S/picoctf-web-exploitation-cookie-monster-secret-recipe-4c1776da9251