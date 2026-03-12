# shark on wire 1

# Descripción

We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap). Recover the flag.
# Solución

```  
picoCTF{StaT31355_636f6e6e}
```
## Pasos para llegar a la solución

- Abrimos Whireshark con el archivo de la captura de datos que nos da el reto
- Seleccionamos cualquier archivo UDP
- Le damos en Follow
	- Después en UDP stream
- Buscando hasta que salga trasmisión  con la bandera
# Notas adicionales

Whireshark:  Es un programa para analizar el trafico de red y retener paquetes

# Referencias











