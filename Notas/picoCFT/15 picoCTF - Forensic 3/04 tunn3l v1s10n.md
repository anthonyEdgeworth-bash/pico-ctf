# tunn3l v1s10n

# Descripción

We found this file. Recover the flag. tunn3l_v1s10n

# Solución

- **Corregir la firma del encabezado (Offset 0x00):** El archivo original tenía caracteres incorrectos al inicio (`BaD`). Se modificaron los primeros bytes para asegurar que comenzara con **`42 4D`** (la firma 'BM' para archivos BMP de Windows) y se ajustó el tamaño del encabezado en los siguientes bytes a **`28 00 00 00`** (40 bytes en decimal) 
- **Corregir el offset de inicio de datos (Offset 0x0A):** Se modificó este valor a **`28 00 00 00`** para indicar correctamente que los datos de la imagen comienzan justo después del encabezado de 40 bytes 
- **Modificar la altura de la imagen (Offset 0x16):** Para revelar la bandera oculta en la parte superior, se incrementó el valor de la altura de la imagen en el encabezado. Inicialmente, cambió el valor en la posición 0x16 a **`40`**  y posteriormente a **`4`** para darle más altura y hacer visible el texto de la bandera 


```  
picoCTF{qu1t3_a_v13w_2020}
```


# Notas adicionales

Comandos usados:

- hexeditor
- exiftool

# Referencias

