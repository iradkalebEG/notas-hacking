# PW Crack 5

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/32/level5.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/32/level5.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/32/level5.hash.bin) in the same directory too. Here's a [dictionary](https://artifacts.picoctf.net/c/32/dictionary.txt) with all possible passwords based on the password conventions we've seen so far.
## Pistas
Opening a file in Python is crucial to using the provided dictionary.
You may need to trim the whitespace from the dictionary word before hashing. Look up the Python string function, `strip`
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/32/level5.py
--2023-03-17 20:49:15--  https://artifacts.picoctf.net/c/32/level5.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.42, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1168 (1.1K) [application/octet-stream]
Saving to: 'level5.py'

level5.py                                 100%[===================================================================================>]   1.14K  --.-KB/s    in 0s      

2023-03-17 20:49:15 (524 MB/s) - 'level5.py' saved [1168/1168]

kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/32/level5.flag.txt.enc
--2023-03-17 20:49:37--  https://artifacts.picoctf.net/c/32/level5.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.42, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level5.flag.txt.enc'

level5.flag.txt.enc                       100%[===================================================================================>]      31  --.-KB/s    in 0s      

2023-03-17 20:49:37 (19.3 MB/s) - 'level5.flag.txt.enc' saved [31/31]

kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/32/level5.hash.bin
--2023-03-17 20:49:50--  https://artifacts.picoctf.net/c/32/level5.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level5.hash.bin'

level5.hash.bin                           100%[===================================================================================>]      16  --.-KB/s    in 0s      

2023-03-17 20:49:50 (8.43 MB/s) - 'level5.hash.bin' saved [16/16]

kilimanjaroo-picoctf@webshell:~$ https://artifacts.picoctf.net/c/32/dictionary.txt
-bash: https://artifacts.picoctf.net/c/32/dictionary.txt: No such file or directory
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/32/dictionary.txt
--2023-03-17 20:50:24--  https://artifacts.picoctf.net/c/32/dictionary.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.74, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 327680 (320K) [application/octet-stream]
Saving to: 'dictionary.txt'

dictionary.txt                            100%[===================================================================================>] 320.00K  1.84MB/s    in 0.2s    

2023-03-17 20:50:24 (1.84 MB/s) - 'dictionary.txt' saved [327680/327680]

kilimanjaroo-picoctf@webshell:~$ nano level5.py 
kilimanjaroo-picoctf@webshell:~$ pwd
/home/kilimanjaroo-picoctf
kilimanjaroo-picoctf@webshell:~$ nano level5.py 
kilimanjaroo-picoctf@webshell:~$ python3 level5.py 
Welcome back... your flag, user:
picoCTF{h45h_sl1ng1ng_40f26f81}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{h45h_sl1ng1ng_40f26f81}

## Notas Adicionales 
comando          descripción

## Referencias