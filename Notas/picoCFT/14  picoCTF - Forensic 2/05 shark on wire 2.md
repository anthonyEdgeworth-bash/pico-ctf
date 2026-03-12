# shark on wire 2

# Descripción

 We found this packet capture. Recover the flag.
# Solución

```  
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```


```  
┌──(kali㉿kali)-[~/Downloads/Forensic02/sharkonwire2]
└─$ sudo apt install python3-scapy 
[sudo] password for kali: 
Upgrading:                      
  python3-scapy
                                                                           
Summary:
  Upgrading: 1, Installing: 0, Removing: 0, Not Upgrading: 1582
  Download size: 2,002 kB
  Space needed: 764 kB / 60.9 GB available

Get:1 http://http.kali.org/kali kali-rolling/main amd64 python3-scapy all 2.7.0+dfsg1-1 [2,002 kB]
Fetched 2,002 kB in 21s (95.1 kB/s)        
(Reading database ... 433764 files and directories currently installed.)
Preparing to unpack .../python3-scapy_2.7.0+dfsg1-1_all.deb ...
Unpacking python3-scapy (2.7.0+dfsg1-1) over (2.6.1+dfsg-1) ...
Setting up python3-scapy (2.7.0+dfsg1-1) ...
Processing triggers for man-db (2.13.1-1) ...
Processing triggers for kali-menu (2025.4.3) ...
                                                                           
┌──(kali㉿kali)-[~/Downloads/Forensic02/sharkonwire2]
└─$ nvim script.py    
                                                                           
┌──(kali㉿kali)-[~/Downloads/Forensic02/sharkonwire2]
└─$ python3 script.py 
picoCTF{p1LLf3r3d_data_v1a_st3g0}
                                                                           
┌──(kali㉿kali)-[~/Downloads/Forensic02/sharkonwire2]
└─$ cat script.py     
from scapy.all import *

packets = rdpcap('capture.pcap')

flag=''

for p in packets:
    if UDP in p and p[UDP].dport == 22:
        if p[UDP].sport > 5000:
            flag+=chr(p[UDP].sport - 5000)

print(flag)
                                                                           
┌──(kali㉿kali)-[~/Downloads/Forensic02/sharkonwire2]
└─$ 

```

# Notas adicionales

- python3-scapy: Sirve para manejar directamente los datos capturados por Whireshark
- script.py: Pequeño programa de python para obtener la bandera
	- Importa la biblioteca scapy de python
	- Carga el archivo con los paquetes obtenidos
	- Crea una variable para obtener dichos datos
	- Un pequeño ciclo para filtrar los datos
	- Imprime la bander
# Referencias







