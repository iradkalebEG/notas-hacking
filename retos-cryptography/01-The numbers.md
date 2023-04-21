# The numbers

## Descripción
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?
## Pistas
The flag is in the format PICOCTF{}
## Solución
```bash
kilimanjaroo-picoctf@webshell:~/criptography$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
--2023-04-17 19:39:33--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100721 (98K) [application/octet-stream]
Saving to: 'the_numbers.png.1'

the_numbers.png.1                               100%[======================================================================================================>]  98.36K  --.-KB/s    in 0.04s   

2023-04-17 19:39:33 (2.21 MB/s) - 'the_numbers.png.1' saved [100721/100721]

kilimanjaroo-picoctf@webshell:~/criptography$ open the_numbers.png
the_numbers.png    the_numbers.png.1  
kilimanjaroo-picoctf@webshell:~/criptography$ open the_numbers.png.1

// a partir de aqui nos abre la imagen con una serie de numeros seguido de
unas llaves que adentro contiene mas numeros, estos numeros representan una letra del abecedario, el 1 = a, el 2 = b, el 3 = c, etc.
por lo que si completamos asi toda la serie de numeros lo que obtendriamos seria lo siguiente
picoCTF{thenumbersmason}
```
## Bandera
picoCTF{thenumbersmason}

## Notas Adicionales 

## Referencias