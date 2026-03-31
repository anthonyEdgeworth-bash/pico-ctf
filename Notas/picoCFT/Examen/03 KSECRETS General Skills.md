# KSECRETS

# Descripción

We have a kubernetes cluster setup and flag is in the secrets. You think you can get it? Please wait for a minute for the application to be configured! Kubernetes is running at: green-hill.picoctf.net : 51453 You can find your configuration file here.
# Solución

```  
picoCTF{ks3cr375_41n7_s4f3_018c4d9b}
```

## Comandos utilizados 


```  
wget http://green-hill.picoctf.net:59011/kubeconfig
--2026-03-28 00:20:33--  http://green-hill.picoctf.net:59011/kubeconfig
Resolving green-hill.picoctf.net (green-hill.picoctf.net)... 3.18.205.4
Connecting to green-hill.picoctf.net (green-hill.picoctf.net)|3.18.205.4|:59011... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2941 (2.9K) [application/octet-stream]
Saving to: ‘kubeconfig’

kubeconfig         100%[================>]   2.87K  --.-KB/s    in 0s      

2026-03-28 00:20:33 (228 MB/s) - ‘kubeconfig’ saved [2941/2941]

                                                                            
┌──(kali㉿kali)-[~/Downloads/Examen]
└─$ nvim kubeconfig 

```

## Archivo Final de configuración de Kuberneters

```  
┌──(kali㉿kali)-[~/Downloads/Examen]
└─$ echo "cGljb0NURntrczNjcjM3NV80MW43X3M0ZjNfMDE4YzRkOWJ9Cg==
" | base64 -d
picoCTF{ks3cr375_41n7_s4f3_018c4d9b}
                                                                            
┌──(kali㉿kali)-[~/Downloads/Examen]
└─$ cat kubeconfig 
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUJlRENDQVIyZ0F3SUJBZ0lCQURBS0JnZ3Foa2pPUFFRREFqQWpNU0V3SHdZRFZRUUREQmhyTTNNdGMyVnkKZG1WeUxXTmhRREUzTnpRMk56RTBPVFV3SGhjTk1qWXdNekk0TURReE9ERTFXaGNOTXpZd016STFNRFF4T0RFMQpXakFqTVNFd0h3WURWUVFEREJock0zTXRjMlZ5ZG1WeUxXTmhRREUzTnpRMk56RTBPVFV3V1RBVEJnY3Foa2pPClBRSUJCZ2dxaGtqT1BRTUJCd05DQUFUNXJ6YlNSeW5wSFhqSGorZTdLdUpzQzkwcUZkV3FMQndDVUNQWkNpaFMKYk1sZE5tRFF6R01mdmFGTENLcStRSis0RGVuTWFneXBaNC9SUllxMXFPOHVvMEl3UURBT0JnTlZIUThCQWY4RQpCQU1DQXFRd0R3WURWUjBUQVFIL0JBVXdBd0VCL3pBZEJnTlZIUTRFRmdRVXUvZTVlOFpxaC8zNDNra2pXdVc4ClR1T0w3QjR3Q2dZSUtvWkl6ajBFQXdJRFNRQXdSZ0loQU8yN1F5U2NnQUlmSXRzTHdSZ2p5eUFhYU9GdERUQzMKekcxU2JXSzlPLy85QWlFQWpQckVCd1BEc2xKbERTR200ejFTNDJkZEZicXVTS2I3TGNxKzA2ZW00K3c9Ci0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0K
    server: https://green-hill.picoctf.net:60941
  name: default
contexts:
- context:
    cluster: default
    user: default
  name: default
current-context: default
kind: Config
users:
- name: default
  user:
    client-certificate-data: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUJrVENDQVRlZ0F3SUJBZ0lJRnp5amZEOURWMXd3Q2dZSUtvWkl6ajBFQXdJd0l6RWhNQjhHQTFVRUF3d1kKYXpOekxXTnNhV1Z1ZEMxallVQXhOemMwTmpjeE5EazFNQjRYRFRJMk1ETXlPREEwTVRneE5Wb1hEVEkzTURNeQpPREEwTVRneE5Wb3dNREVYTUJVR0ExVUVDaE1PYzNsemRHVnRPbTFoYzNSbGNuTXhGVEFUQmdOVkJBTVRESE41CmMzUmxiVHBoWkcxcGJqQlpNQk1HQnlxR1NNNDlBZ0VHQ0NxR1NNNDlBd0VIQTBJQUJOa0pYOGczNDY0b2VlRysKazg0U1VCaDJtTElEQkRWUzI3MGx2T3hNM0VhZTBlMGxrQ1ZUbTZJMUhNMkwxZFRYT2NIVkY5dU5NdnlFYm16MQo3dFNpMk1talNEQkdNQTRHQTFVZER3RUIvd1FFQXdJRm9EQVRCZ05WSFNVRUREQUtCZ2dyQmdFRkJRY0RBakFmCkJnTlZIU01FR0RBV2dCU0lzMUpZK1lXZUo3NEEzaUFnUW5xOW5RQmlpVEFLQmdncWhrak9QUVFEQWdOSUFEQkYKQWlFQTBuUVdMdzFwY1R3RTVqWW9NZXNuSHFCSmFTNVJJcTYrWW1jdkZXUTJiTk1DSUhMS1NleXpGQk44Q3ZrRwoyUW04K2lHSHo3aG5YMk14NFZaNXZKaXF3aTlkCi0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0KLS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUJkakNDQVIyZ0F3SUJBZ0lCQURBS0JnZ3Foa2pPUFFRREFqQWpNU0V3SHdZRFZRUUREQmhyTTNNdFkyeHAKWlc1MExXTmhRREUzTnpRMk56RTBPVFV3SGhjTk1qWXdNekk0TURReE9ERTFXaGNOTXpZd016STFNRFF4T0RFMQpXakFqTVNFd0h3WURWUVFEREJock0zTXRZMnhwWlc1MExXTmhRREUzTnpRMk56RTBPVFV3V1RBVEJnY3Foa2pPClBRSUJCZ2dxaGtqT1BRTUJCd05DQUFRckJXWlUwYXNZT0ordDMxbks4TGw0TklORUJjODFQNmdpOVRQcTV1a3YKRWNuSm9yQWpDWlZxVlZjV05WRjlNemNJRUliUEtOZG55Z1FtQi92cW1TR1RvMEl3UURBT0JnTlZIUThCQWY4RQpCQU1DQXFRd0R3WURWUjBUQVFIL0JBVXdBd0VCL3pBZEJnTlZIUTRFRmdRVWlMTlNXUG1GbmllK0FONGdJRUo2CnZaMEFZb2t3Q2dZSUtvWkl6ajBFQXdJRFJ3QXdSQUlnSWh5d2Y5Z2N5Q3d1aXNNTUtDZHZsZEZnbTRmNEwxSHgKSEFxeTJjbm41bVlDSUJpR1RyZ0xxbXF1V3A2QjFBKzlhcW4yM1UxWHFTRTFkSDdCZWNDbGlwOWkKLS0tLS1FTkQgQ0VSVElGSUNBVEUtLS0tLQo=
    client-key-data: LS0tLS1CRUdJTiBFQyBQUklWQVRFIEtFWS0tLS0tCk1IY0NBUUVFSUNhRS94TXVwbDZCRkZ5R1BuZUFYTThCZWxYZjZvQWpjaTl5djBsSHl6czJvQW9HQ0NxR1NNNDkKQXdFSG9VUURRZ0FFMlFsZnlEZmpyaWg1NGI2VHpoSlFHSGFZc2dNRU5WTGJ2U1c4N0V6Y1JwN1I3U1dRSlZPYgpvalVjell2VjFOYzV3ZFVYMjQweS9JUnViUFh1MUtMWXlRPT0KLS0tLS1FTkQgRUMgUFJJVkFURSBLRVktLS0tLQo=
                               
```

```  
┌──(kali㉿kali)-[~/Downloads/Examen]
└─$ kubectl get secret ctf-secret -n picoctf -o yaml --insecure-skip-tls-verify
apiVersion: v1
data:
  flag: cGljb0NURntrczNjcjM3NV80MW43X3M0ZjNfMDE4YzRkOWJ9Cg==
kind: Secret
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"v1","data":{"flag":"cGljb0NURntrczNjcjM3NV80MW43X3M0ZjNfMDE4YzRkOWJ9Cg=="},"kind":"Secret","metadata":{"annotations":{},"name":"ctf-secret","namespace":"picoctf"},"type":"Opaque"}
  creationTimestamp: "2026-03-28T04:18:32Z"
  name: ctf-secret
  namespace: picoctf
  resourceVersion: "387"
  uid: 27e0719a-9688-429d-aa36-a19a2209f3de
type: Opaque
                                                                            
┌──(kali㉿kali)-[~/Downloads/Examen]
└─$ echo "cGljb0NURntrczNjcjM3NV80MW43X3M0ZjNfMDE4YzRkOWJ9Cg==
" | base64 -d
picoCTF{ks3cr375_41n7_s4f3_018c4d9b}

```


# Notas adicionales


# Referencias

