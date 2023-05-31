# transposition-trial

## Descripción
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://artifacts.picoctf.net/c/191/message.txt).
## Pistas
Split the message up into blocks of 3 and see how the first block is scrambled
## Solución
```bash
┌──(kali㉿kali)-[~/Documents/reversing/transpositions-trial]
└─$ wget https://artifacts.picoctf.net/c/191/message.txt
--2023-05-16 17:36:42--  https://artifacts.picoctf.net/c/191/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.74, 18.154.132.88, 18.154.132.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 54 [application/octet-stream]
Saving to: ‘message.txt’

message.txt          100%[===================>]      54  --.-KB/s    in 0s      

2023-05-16 17:36:43 (26.6 MB/s) - ‘message.txt’ saved [54/54]

                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing/transpositions-trial]
└─$ cat message.txt        
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4 
```
Nos vamos a esta direccion:
https://tholman.com/other/transposition/
y pegamos lo que contiene el archivo
nuestra llave es 3
y acomodamos las columnas en orden:
201
## Bandera
picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A}  

## Notas Adicionales 

## Referencias