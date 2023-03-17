# PW Crack 3

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Pistas
To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
To exit `bvi` type `:q` and press enter.
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.py
--2023-03-17 20:08:48--  https://artifacts.picoctf.net/c/17/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.42, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                                 100%[===================================================================================>]   1.31K  --.-KB/s    in 0s      

2023-03-17 20:08:48 (4.92 MB/s) - 'level3.py' saved [1337/1337]

kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
--2023-03-17 20:09:00--  https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.42, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                       100%[===================================================================================>]      31  --.-KB/s    in 0s      

2023-03-17 20:09:00 (31.1 MB/s) - 'level3.flag.txt.enc' saved [31/31]

kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.hash.bin
--2023-03-17 20:09:20--  https://artifacts.picoctf.net/c/17/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                           100%[===================================================================================>]      16  --.-KB/s    in 0s      

2023-03-17 20:09:20 (6.78 MB/s) - 'level3.hash.bin' saved [16/16]

kilimanjaroo-picoctf@webshell:~$ nano level3.py 
kilimanjaroo-picoctf@webshell:~$ python 3 level3.py 
python: can't open file '/home/kilimanjaroo-picoctf/3': [Errno 2] No such file or directory
kilimanjaroo-picoctf@webshell:~$ python3 level3.py 
  File "/home/kilimanjaroo-picoctf/level3.py", line 46
    level_3_pw_check(ps)
    ^
IndentationError: expected an indented block after 'for' statement on line 45
kilimanjaroo-picoctf@webshell:~$ nano level3.py 
kilimanjaroo-picoctf@webshell:~$ python3 level3.py 
Traceback (most recent call last):
  File "/home/kilimanjaroo-picoctf/level3.py", line 45, in <module>
    for ps in pow_pw_list:
NameError: name 'pow_pw_list' is not defined. Did you mean: 'pos_pw_list'?
kilimanjaroo-picoctf@webshell:~$ nano level3.py 
kilimanjaroo-picoctf@webshell:~$ python3 level3.py 
That password is incorrect
That password is incorrect
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
That password is incorrect
That password is incorrect
That password is incorrect
That password is incorrect
kilimanjaroo-picoctf@webshell:~$ 
```
## Bandera
picoCTF{m45h_fl1ng1ng_cd6ed2eb}

## Notas Adicionales 
comando          descripción

## Referencias