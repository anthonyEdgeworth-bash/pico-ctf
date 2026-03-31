## RETO
FANTASY CTF
## DESCRIPCION
Play this short game to get familiar with terminal applications and some of the most important rules in scope for picoCTF.Connect to the program with netcat:`$ nc verbal-sleep.picoctf.net 59954`
## SOLUCION


```  
picoCTF{m1113n1um_3d1710n_dd015572}
```


──(kali㉿kali)-[~]
└─$ nc verbal-sleep.picoctf.net 59954
FANTASY CTF SIMULATION

The simulation begins in the private room of Eibhilin, a bright, young student.
The room is dimly lit, with the glow of her multiple monitors casting an
electric blue hue on the walls. Around the room are posters of vintage movies
from the MCU — ancient guardians from another age staring down like digital
sentinels.

---
(Press Enter to continue...)
---

Eibhilin stretches back in her chair, adjusting the holo-display of her
keyboard. A soft hum of a nearby server fills the air as her AI companion,
`Nyx`, comes to life.

---
(Press Enter to continue...)
---

"Good evening, Ei," Nyx chirps, "The 3025 edition of picoCTF registration is
open. You asked me to remind so you could try out the competition for the first
time. Do you wish to proceed?"

---
(Press Enter to continue...)
---

Outside, the city of Nexalus glimmers under the stars, but Eibhilin's focus
remains entirely on the screen in front of her.

---
(Press Enter to continue...)
---

"Yes, Nyx. Let's do it!"

---
(Press Enter to continue...)
---

Nyx brings up the registration page.

Options:
A) *Register multiple accounts*
B) *Share an account with a friend*
C) *Register a single, private account*
[a/b/c] > a

Nyx chimes in, "Eibhilin, don't do that! That's been grounds for
disqualification for the past 1,000 years!"

---
(Press Enter to continue...)
---

"Oh, thanks Nyx, that was close!"

---
(Press Enter to continue...)
---

"Ok," Nyx says, "Registering you for the competition... There's an introductory
audio message, piping to your speakers."

---
(Press Enter to continue...)
---

"Welcome hacker! You're about to embark on a journey that will teach you many
esoteric and valuable skills. Our mission is to guide you in the right path,
that you may use these skills to protect and defend and never for selfish gain
or deceit. We hope you enjoy the challenges that our authors have devised this
year. Always remember: 'With great power, comes great responsibility!'"

---
(Press Enter to continue...)
---

Nyx continues, "I've gleaned from the Ether that in CTF competitions, it's
always good to start with the 'sanity' challenge. It should be the challenge
worth the least amount of points. I'll pull it up. You're looking for something
called the flag. You should know it when you see it."

---
(Press Enter to continue...)
---

"Oh interesting," Eibhilin says, "It seems like the sanity challenge is an old
school interactive fiction game."

---
(Press Enter to continue...)
---

Options:
A) *Play the game*
B) *Search the Ether for the flag*
[a/b] > a

"Good choice, Ei," Nyx says, "You never want to share flags or artifact
downloads."

---
(Press Enter to continue...)
---

 Playing the Game
Playing the Game: 100%|██████████████████████████████████████ [time left: 00:00]
Playing the Game completed successfully!

---
(Press Enter to continue...)
---

"That was fun!" Eibhilin exclaims, "I found the flag!"

---
(Press Enter to continue...)
---
 
Nyx says, "Great job, Ei! I've read that a lot of players create writeups of
interesting challenges they solve during the competition. Just be sure to wait
to publish them until after the winners have been announced. We can work on
that together if you'd like."
(Press Enter to continue...)
---

"Thanks, Nyx! Here's the flag I found: picoCTF{m1113n1um_3d1710n_dd015572}"

## NOTAS ADICIONALES
- **Netcat como herramienta de depuración:** Este reto demuestra la versatilidad de `nc` para interactuar con servicios de red simples sin necesidad de un cliente especializado.
    
- **Sanity Check:** Este tipo de retos se clasifican como "comprobación de estado", diseñados para verificar que el entorno de trabajo del competidor (terminal, conectividad y salida de red) funciona correctamente antes de enfrentar retos de mayor complejidad técnica.
    
- **Comportamiento del programa:** El programa acepta valores por defecto al recibir un "Enter" vacío, lo que permite completar la secuencia de comandos y llegar a la función que despliega la bandera.
## REFERENCIAS