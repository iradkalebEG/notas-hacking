# Mus1c

## Descripción
I wrote you a [song](https://jupiter.challenges.picoctf.org/static/c0863a3b0170d6dd176be3a595b4b75e/lyrics.txt). Put it in the picoCTF{} flag format.
## Pistas
Do you think you can master rockstar?
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/c0863a3b0170d6dd176be3a595b4b75e/lyrics.txt
--2023-03-06 04:10:52--  https://jupiter.challenges.picoctf.org/static/c0863a3b0170d6dd176be3a595b4b75e/lyrics.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 772 [application/octet-stream]
Saving to: 'lyrics.txt'

lyrics.txt                                100%[====================================================================================>]     772  --.-KB/s    in 0s      

2023-03-06 04:10:52 (72.4 MB/s) - 'lyrics.txt' saved [772/772]

kilimanjaroo-picoctf@webshell:~$ ls
README.txt  bandera  bandera.txt  file  lyrics.txt  nano.241.save  strings
kilimanjaroo-picoctf@webshell:~$ cat lyrics.txt 
Pico's a CTFFFFFFF
my mind is waitin
It's waitin

Put my mind of Pico into This
my flag is not found
put This into my flag
put my flag into Pico


shout Pico
shout Pico
shout Pico

My song's something
put Pico into This

Knock This down, down, down
put This into CTF

shout CTF
my lyric is nothing
Put This without my song into my lyric
Knock my lyric down, down, down

shout my lyric

Put my lyric into This
Put my song with This into my lyric
Knock my lyric down

shout my lyric

Build my lyric up, up ,up

shout my lyric
shout Pico
shout It

Pico CTF is fun
security is important
Fun is fun
Put security with fun into Pico CTF
Build Fun up
shout fun times Pico CTF
put fun times Pico CTF into my song

build it up

shout it
shout it

build it up, up
shout it
shout Picokilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{rrrocknrn0113r}

## Notas Adicionales 
Una vez que descargas el archivo hay que abrirlo, copiar el texto que incluye y llevarlo a una 
pagina que convierte ese texto en código ascii y por ultimo cambiar ese código en texto otra vez

## Referencias
https://codewithrockstar.com/online
https://www.duplichecker.com/ascii-to-text.php