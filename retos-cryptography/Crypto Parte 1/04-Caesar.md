# Caesar

## Descripción
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).
## Pistas
caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)
## Solución
```bash
kilimanjaroo-picoctf@webshell:~/criptography/caesar$ wget https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
--2023-04-20 18:29:57--  https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 35 [application/octet-stream]
Saving to: 'ciphertext'

ciphertext           100%[====================>]      35  --.-KB/s    in 0s      

2023-04-20 18:29:57 (18.8 MB/s) - 'ciphertext' saved [35/35]

kilimanjaroo-picoctf@webshell:~/criptography/caesar$ ls
ciphertext
kilimanjaroo-picoctf@webshell:~/criptography/caesar$ open ciphertext 
Warning: unknown mime-type for "ciphertext" -- using "application/octet-stream"
Error: no "view" mailcap rules found for type "application/octet-stream"


Exiting via interrupt: 2


kilimanjaroo-picoctf@webshell:~/criptography/caesar$ open ciphertext
'Como sugieren el título y la sugerencia del problema, esto está codificado con un cifrado César, en el que cada carácter se desplaza varias veces en el alfabeto. Simplemente inserte la bandera del archivo en una herramienta en línea como [Cryptii](https://cryptii.com/pipes/caesar-cipher) y cambie el valor desplazado hasta que el texto sin formato se convierta en un mensaje coherente.''
```
## Bandera
picoCTF{crossingtherubiconvfhsjkou}

## Notas Adicionales 
comando          descripción

## Referencias