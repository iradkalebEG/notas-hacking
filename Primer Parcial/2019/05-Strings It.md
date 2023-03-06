# Strings It

## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?
## Pistas
[strings](https://linux.die.net/man/1/strings)
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings 
--2023-03-02 19:07:19--  https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                 100%[============================>] 757.84K  1.85MB/s    in 0.4s    

2023-03-02 19:07:19 (1.85 MB/s) - 'strings' saved [776032/776032]

kilimanjaroo-picoctf@webshell:~$ ls
README.txt  strings
kilimanjaroo-picoctf@webshell:~$ string strings | grep pico
-bash: string: command not found
kilimanjaroo-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_d66c7bb7}
kilimanjaroo-picoctf@webshell:~$ 
```
## Bandera
picoCTF{5tRIng5_1T_d66c7bb7}

## Notas Adicionales 
comando          descripción

## Referencias