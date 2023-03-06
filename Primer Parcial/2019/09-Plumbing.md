# Plumbing

## Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.
## Pistas
Remember the flag format is picoCTF{XXXX}.
What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 > bandera.txt

kilimanjaroo-picoctf@webshell:~$ ls
README.txt  bandera  bandera.txt  file  nano.241.save  strings
kilimanjaroo-picoctf@webshell:~$ cat bandera.txt | grep picoCTF*
picoCTF{digital_plumb3r_ea8bfec7}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{digital_plumb3r_ea8bfec7}

## Notas Adicionales 
comando          descripción

## Referencias