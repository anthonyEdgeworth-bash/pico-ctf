# Binary Search

# Descripción

Description
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses. Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools! You can download the challenge files here:

    challenge.zip

ssh -p 59156 ctf-player@atlas.picoctf.net Using the password 6abf4a82. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
# Solución

```  
picoCTF{g00d_gu355_bee04a2a}
```

```  
┌──(kali㉿kali)-[~/…/Binary-Search/home/ctf-player/drop-in]
└─$ ssh -p 49717 ctf-player@atlas.picoctf.net
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Lower! Try again.
Enter your guess: 125
Lower! Try again.
Enter your guess: 60
Higher! Try again.
Enter your guess: 80
Lower! Try again.
Enter your guess: 70
Congratulations! You guessed the correct number: 70
Here's your flag: picoCTF{g00d_gu355_bee04a2a}
Connection to atlas.picoctf.net closed.
                                                                                                        
┌──(kali㉿kali)-[~/…/Binary-Search/home/ctf-player/drop-in]
└─$ s s s


```

# Notas adicionales

Para la búsqueda binaria, se basa simplemente en mitades; búsquedas a partir de la mitad
# Referencias

[medium](https://medium.com/@chiragvyas369/binary-search-walkthrough-78dc6b232e85)