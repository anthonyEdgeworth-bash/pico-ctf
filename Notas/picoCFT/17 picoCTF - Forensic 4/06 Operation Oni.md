# Reto

# Descripción

Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.

    Download disk image
    Remote machine: ssh -i key_file -p 52501 ctf-player@saturn.picoctf.net

# Solución

```  
picoCTF{k3y_5l3u7h_af277f77}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ gzip -d disk.flag.img.gz 
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ fls -o 411648 disk.flag.img
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ icat -i raw -o 411648 disk.flag.img 1875
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ icat -o 411648  disk.flag.img 1782
Salted__S�+%���+�O��k�ђ(A����c��
                                @]ԣ
L�ޢȤ7� ���؎$�'%                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ icat -o 411648  disk.flag.img 1782 > flag.txt.enc
                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40378722AF7F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ cat flag.txt
picoCTF{h4un71ng_p457_1d02081e}                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ 7_1d02081e}                                                                                                                                                            
zsh: parse error near `}'
                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOrchid]
└─$ cd ..                                                       
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041]
└─$ mkdir OperationOni   
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041]
└─$ cd OperationO     
cd: no such file or directory: OperationO
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041]
└─$ cd OperationOni 
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ wget 'https://artifacts.picoctf.net/c/71/disk.img.gz'
--2026-04-12 01:22:56--  https://artifacts.picoctf.net/c/71/disk.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.26, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 48132743 (46M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz        100%[================>]  45.90M  13.7MB/s    in 3.6s    

2026-04-12 01:23:00 (12.9 MB/s) - ‘disk.img.gz’ saved [48132743/48132743]

                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ gzip -d disk.flag.img.gz
Completing external command
g++                       gpg-agent               
g++-15                    gpgconf                 
g3topbm                   gpg-connect-agent       
galera_new_cluster        gpg-mail-tube           
galera_recovery           gpgparsemail            
gamma4scanimage           gpgsm                   
gapplication              gpgsplit                
gatttool                  gpgtar                  
gawk                      gpgv                    
gawkbug                   gpg-wks-client          
gbb_utility               gpic                    
gcc                       gpp-decrypt             
gcc-15                    gprof                   
gcc-ar                    gprofng                 
gcc-ar-15                 gprofng-archive         
gcc-nm                    gprofng-collect-app     
gcc-nm-15                 gprofng-display-html    
gcc-ranlib                gprofng-display-src     
gcc-ranlib-15             gprofng-display-text    
gcov                      gprofng-gmon            
gcov-15                   greenbone-certdata-sync 
gcov-dump                 greenbone-feed-sync     
gcov-dump-15              greenbone-nvt-sync      
gcov-tool                 greenbone-scapdata-sync 
gcov-tool-15              gregorio                
gcr-viewer                grep                    
gcr-viewer-gtk4           gresource               
gdbus                     groff                   
gdisk                     grog                    
geli2john                 grops                   
gem                       grotty                  
gem3.3                    groupadd                
gemtopbm                  groupdel                
gemtopnm                  groupmod                
gencat                    groups                  
gendiff                   grpck                   
generic_chunked           grpconv                 
generic_listen_tcp        grpunconv               
generic_send_tcp          grub-bios-setup         
generic_send_udp          grub-editenv            
generic_web_server_fuzz   grub-file               
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ gzip -d disk.flag.img.gz
gzip: disk.flag.img.gz: No such file or directory
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ ls
disk.img.gz
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ gzip -d disk.img.gz     
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ reset
Erase is control-H (^H).
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ ls
disk.img
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ mmls disk.img     
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ fls -o 206848 disk.img     
d/d 458:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 79: proc
d/d 80: dev
d/d 81: tmp
d/d 82: lib
d/d 85: var
d/d 94: usr
d/d 104:        bin
d/d 118:        sbin
d/d 464:        media
d/d 468:        mnt
d/d 469:        opt
d/d 470:        root
d/d 471:        run
d/d 473:        srv
d/d 474:        sys
V/V 33049:      $OrphanFiles
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ fls -o 206848 disk.img 470
r/r 2344:       .ash_history
d/d 3916:       .ssh
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ fls -o 206848 disk.img 3916 
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ icat -o 206848 disk.img 2345             
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ icat -o 206848 disk.img 2345 > key_file
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$ chmod 400 key_file 
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/OperationOni]
└─$  ssh -i key_file -p 52501 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:52501 ([13.59.203.175]:52501)' can't be established.
ED25519 key fingerprint is: SHA256:XBSvB1lk28EctsAVdKJtsl0A7C5bonqPrvHCYH8aEy4
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:52501' (ED25519) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.8.0-1047-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt 
picoCTF{k3y_5l3u7h_af277f77}ctf-player@challenge:~$ ^C
ctf-player@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
                                                      
```


# Notas adicionales

## Comandos usados

- mmls
	- Muestra las particiones de la imagen
- fls -o 206848
	- Enlistamos los archivos de dicho inodo
- icat -o 206848
	- Muestra el contenido del archivo de dicho inodo


# Referencias


https://www.youtube.com/watch?v=PVeV-S3Zbqk

