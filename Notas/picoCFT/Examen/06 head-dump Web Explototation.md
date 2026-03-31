# head-dump

# Descripción

Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag. The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden. The website is running picoCTF News.

# Solución

```  
picoCTF{Pat!3nt_15_Th3_K3y_59106086}
```

## Pasos para llegar a la solución

- Ingresar al sitio web
- ingresar a "# swagger  UI"
- Ir a la sección Diagnosing 
- Descargar el archivo heapdump
- Usar el comando:
	- cat heapdump.heapsnapshot | grep "picoCTF" 

# Notas adicionales


# Referencias

https://medium.com/@rahmeez/picoctf-head-dump-writeup-2455761c362d

