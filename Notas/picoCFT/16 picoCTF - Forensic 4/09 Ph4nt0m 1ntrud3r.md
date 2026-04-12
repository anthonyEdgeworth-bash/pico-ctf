# Ph4nt0m 1ntrud3r

# Descripción

A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! Find the PCAP file here Network Traffic PCAP file and try to get the flag. 
# Solución

```  
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_d4b57909}
```

## Pasos para llegar a la solución

```  
1. Abrir el paquete con Wireshark+
   Filtrar por tcp.len==12 || tcp.len==4
   Ordenar el tiempo
   Seleccionar un paquete
   Seleccionar Retrabsmitted TCP segment data
	   Seleccionar Show Packet Bytes
	   Decode as Base64
```


# Notas adicionales

## Comandos usados

# Referencias

https://www.youtube.com/watch?v=_YKC5Smffeg

