# Serpentine

## Descripción
Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/37/serpentine.py)
## Pistas
Try running the script and see what happens
In the webshell, try examining the script with a text editor like `nano`
To exit `nano`, press Ctrl and x and follow the on-screen prompts.
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/37/serpentine.py
--2023-03-17 21:07:26--  https://artifacts.picoctf.net/c/37/serpentine.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.120, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2550 (2.5K) [application/octet-stream]
Saving to: 'serpentine.py'

serpentine.py                             100%[===================================================================================>]   2.49K  --.-KB/s    in 0s      

2023-03-17 21:07:26 (1.14 GB/s) - 'serpentine.py' saved [2550/2550]

kilimanjaroo-picoctf@webshell:~$ nano serpentine.py 
kilimanjaroo-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5c) + chr(0x01) + chr(0x57) + chr(0x2a) + chr(0x17) >
  File "<stdin>", line 1
    chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5c) + chr(0x01) + chr(0x57) + chr(0x2a) + chr(0x17) >
                                                                                                                                                               ^
SyntaxError: invalid syntax
>>> chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5c) + chr(0x01) + chr(0x57) + chr(0x2a) + chr(0x17)
"\x15\x07\x08\x06'!#\x15\\\x01W*\x17"
>>> chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5c) + chr(0x01) + chr(0x57) + chr(0x2a) + chr(0x17) + chr(0x5e) + chr(0x5f) + chr(0x0d) + chr(0x3b) + chr(0x19) + chr(0x56) + chr(0x5b) + chr(0x5e) + chr(0x36) + chr(0x53) + chr(0x07) + chr(0x51) + chr(0x18) + chr(0x58) + chr(0x05) + chr(0x57) + chr(0x11) + chr(0x3a) + chr(0x56) + chr(0x0e) + chr(0x5d) + chr(0x53) + chr(0x11) + chr(0x54) + chr(0x5c) + chr(0x53) + chr(0x14)
"\x15\x07\x08\x06'!#\x15\\\x01W*\x17^_\r;\x19V[^6S\x07Q\x18X\x05W\x11:V\x0e]S\x11T\\S\x14"
>>> 
kilimanjaroo-picoctf@webshell:~$ python3 serpentine.py 

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) c
kilimanjaroo-picoctf@webshell:~$ nano serpentine.py 
kilimanjaroo-picoctf@webshell:~$ python3 serpentine.py 
picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}

## Notas Adicionales 
comando          descripción

## Referencias