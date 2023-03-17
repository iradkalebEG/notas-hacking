# PW Crack 2

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.
## Pistas
Does that encoding look familiar?
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.py
--2023-03-17 19:58:09--  https://artifacts.picoctf.net/c/13/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.6, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                 100%[===================================================================================>]     914  --.-KB/s    in 0s      

2023-03-17 19:58:09 (420 MB/s) - 'level2.py' saved [914/914]

kilimanjaroo-picoctf@webshell:~$ nano level2.py 
kilimanjaroo-picoctf@webshell:~$ python3 level2.py 
Traceback (most recent call last):
  File "/home/kilimanjaroo-picoctf/level2.py", line 12, in <module>
    flag_enc = open('level2.flag.txt.enc', 'rb').read()
FileNotFoundError: [Errno 2] No such file or directory: 'level2.flag.txt.enc'
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
--2023-03-17 19:59:23--  https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.6, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                       100%[===================================================================================>]      31  --.-KB/s    in 0s      

2023-03-17 19:59:23 (1.60 MB/s) - 'level2.flag.txt.enc' saved [31/31]

kilimanjaroo-picoctf@webshell:~$ python3 level2.py 
Please enter correct password for flag: 
That password is incorrect
kilimanjaroo-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
kilimanjaroo-picoctf@webshell:~$ nano level2.py 
kilimanjaroo-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
kilimanjaroo-picoctf@webshell:~$ nano level2.py 
kilimanjaroo-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)
'de76'
>>> 
kilimanjaroo-picoctf@webshell:~$ python3 level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{tr45h_51ng1ng_489dea9a}

## Notas Adicionales 
comando          descripción

## Referencias