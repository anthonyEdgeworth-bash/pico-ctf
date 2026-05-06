# vault-door-3

# Descripción

This vault uses for-loops and byte arrays. The source code for this vault is here: VaultDoor3.java
# Solución

```  
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_f66133}
```

## Pasos para llegar a la solución

```  
Al código que nos dan hacer estás modificaciones:

        System.out.println(buffer);
        String s = new String(buffer);
        return s.equals("jU5t_a_sna_3lpm13g64f_u_4_m6r143");
Al final del código

- Ejecutar el código:
  ┌──(kali㉿kali)-[~/Downloads/Reversing01/vault-door-3]
└─$ javac VaultDoor3.java && java VaultDoor3
Enter vault password: picoCTF{jU5t_a_sna_3lpm13g64f_u_4_m6r143}
jU5t_a_s1mpl3_an4gr4m_4_u_f66133
Access denied!
                    
- Ejecutar con está bandera:
                                                
┌──(kali㉿kali)-[~/Downloads/Reversing01/vault-door-3]
└─$ javac VaultDoor3.java && java VaultDoor3
Enter vault password: picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_f66133}
jU5t_a_sna_3lpm13g64f_u_4_m6r143
Access granted.

```


# Notas adicionales

## Comandos usados

# Referencias

https://youtu.be/rOmE3JYUlLY