# Glitch Cat

## Descripción
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 50561`
## Pistas
ASCII is one of the most common encodings used in programming
We know that the glitch output is valid Python, somehow!
Press Ctrl and c on your keyboard to close your connection and return to the command prompt.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ nc saturn.picoctf.net 50561
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'


kilimanjaroo-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
'picoCTF{gl17ch_m3_n07_9c42a45d}'
>>> 
```
## Bandera
picoCTF{gl17ch_m3_n07_9c42a45d}

## Notas Adicionales 
comando          descripción

## Referencias