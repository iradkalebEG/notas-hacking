# PW Crack 1

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/11/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/11/level1.flag.txt.enc) in the same directory too.
## Pistas
To view the file in the webshell, do: `$ nano level1.py`
To exit `nano`, press Ctrl and x and follow the on-screen prompts.
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/11/level1.py
--2023-03-17 19:52:07--  https://artifacts.picoctf.net/c/11/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.120, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                 100%[===================================================================================>]     876  --.-KB/s    in 0s      

2023-03-17 19:52:07 (4.90 MB/s) - 'level1.py' saved [876/876]

kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
--2023-03-17 19:52:26--  https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.6, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                       100%[===================================================================================>]      30  --.-KB/s    in 0s      

2023-03-17 19:52:26 (16.7 MB/s) - 'level1.flag.txt.enc' saved [30/30]

kilimanjaroo-picoctf@webshell:~$ cat level1.flag.txt.enc 
A
 Rr1wQ  nVT_nPRVWkilimanjaroo-picoctf@webshell:~$ nano level1.flag.txt.enc 
kilimanjaroo-picoctf@webshell:~$ nano level1.py 
kilimanjaroo-picoctf@webshell:~$ python3 level1.py 
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{545h_r1ng1ng_fa343060}

## Notas Adicionales 
comando          descripción

## Referencias