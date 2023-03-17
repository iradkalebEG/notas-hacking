# PW Crack 4

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/21/level4.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/21/level4.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/21/level4.hash.bin) in the same directory too.There are 100 potential passwords with only 1 being correct. You can find these by examining the password checker script.
## Pistas
A for loop can help you do many things very quickly.
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/21/level4.py
--2023-03-17 20:36:39--  https://artifacts.picoctf.net/c/21/level4.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.120, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2085 (2.0K) [application/octet-stream]
Saving to: 'level4.py'

level4.py                                 100%[===================================================================================>]   2.04K  --.-KB/s    in 0s      

2023-03-17 20:36:39 (913 MB/s) - 'level4.py' saved [2085/2085]

kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/21/level4.flag.txt.enc
--2023-03-17 20:36:52--  https://artifacts.picoctf.net/c/21/level4.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: 'level4.flag.txt.enc'

level4.flag.txt.enc                       100%[===================================================================================>]      33  --.-KB/s    in 0s      

2023-03-17 20:36:52 (15.5 MB/s) - 'level4.flag.txt.enc' saved [33/33]

kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/21/level4.hash.bin
--2023-03-17 20:37:05--  https://artifacts.picoctf.net/c/21/level4.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.42, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level4.hash.bin'

level4.hash.bin                           100%[===================================================================================>]      16  --.-KB/s    in 0s      

2023-03-17 20:37:05 (658 KB/s) - 'level4.hash.bin' saved [16/16]

kilimanjaroo-picoctf@webshell:~$ nano level4.py 
kilimanjaroo-picoctf@webshell:~$ python3 level4.py 
Traceback (most recent call last):
  File "/home/kilimanjaroo-picoctf/level4.py", line 41, in <module>
    for pw in pso_pw_list:
NameError: name 'pso_pw_list' is not defined. Did you mean: 'pos_pw_list'?
kilimanjaroo-picoctf@webshell:~$ nano level4.py 

kilimanjaroo-picoctf@webshell:~$ python3 level4.py 
Welcome back... your flag, user:
picoCTF{fl45h_5pr1ng1ng_d770d48c}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{fl45h_5pr1ng1ng_d770d48c}

## Notas Adicionales 
comando          descripción

## Referencias