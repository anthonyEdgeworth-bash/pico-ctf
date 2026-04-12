# Milkslap

# Descripción

Description
🥛 http://wily-courier.picoctf.net:56833/
# Solución

```  
picoCTF{imag3_m4n1pul4t10n_sl4p5}
```

## Pasos para llegar a la solución

```  
┌──(kali㉿kali)-[~/Downloads/Forensic041/Milkslap]
└─$ export RUBY_THREAD_VM_STACK_SIZE=500000000
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/Milkslap]
└─$ zsteg concat_v.png          
imagedata           .. text: "\n\n\n\n\n\n\t\t"
chunk:0:IHDR        .. file: Adobe Photoshop Color swatch, version 0, 1280 c 0, y 0, z 0
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
b1,bgr,lsb,xy       .. <wbStego size=0x941a5b ext=nil data="\xB6\xAD\xB6}\xDF7\x7F\xDB\xDFI\bm\xDB\xDB\x80m\x00\x00\x00\xB6m\xDB\xDB\xB6\x00\x00\x00\xB6xDB\xB6mm\xDB\xB6\xB6\x00\x00\x00\x00\x00m\xDB" even=true hdr=nil enc=nil mi
b2,r,lsb,xy         .. text: ["U" repeated 8 times]
b2,r,msb,xy         .. file: VISX image file
b2,g,lsb,xy         .. file: VISX image file
b2,g,msb,xy         .. file: SoftQuad DESC or font file binary - version 157
b2,b,msb,xy         .. text: "UfUUUU@UUU"
b4,r,lsb,xy         .. text: "\"\"\"\"\"#4D"
b4,r,msb,xy         .. text: "wwww3333"
b4,g,lsb,xy         .. text: "wewwwwvUS"
b4,g,msb,xy         .. text: "\"\"\"\"DDDD"
b4,b,lsb,xy         .. text: "vdUeVwweDFw"
b4,b,msb,xy         .. text: "UUYYUUUUUUUU"
                                                                            
┌──(kali㉿kali)-[~/Downloads/Forensic041/Milkslap]
└─$                             

```


# Notas adicionales

## Comandos usados

- zsteg
	- Comando usado para ver los metadatos de la imagen

# Referencias

