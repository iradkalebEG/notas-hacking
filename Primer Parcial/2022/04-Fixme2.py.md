# Fixme2.py

## Descripción
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/5/fixme2.py)
## Pistas
Are equality and assignment the same symbol?
To view the file in the webshell, do: `$ nano fixme2.py`
To exit `nano`, press Ctrl and x and follow the on-screen prompts.
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/5/fixme2.py
--2023-03-17 19:21:19--  https://artifacts.picoctf.net/c/5/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.42, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                                 100%[===================================================================================>]   1.00K  --.-KB/s    in 0s      

2023-03-17 19:21:19 (296 MB/s) - 'fixme2.py' saved [1029/1029]

kilimanjaroo-picoctf@webshell:~$ ls
Addadshashanammu      README.txt  bandera.txt  codebook.txt  ende.py  fixme1.py  flag         ltdis.sh    lyrics.txt.1   pw.txt  static.ltdis.strings.txt  strings
Addadshashanammu.zip  bandera     code.py      convertme.py  file     fixme2.py  flag.txt.en  lyrics.txt  nano.241.save  static  static.ltdis.x86_64.txt   warm
kilimanjaroo-picoctf@webshell:~$ python3 fixme2.py 
  File "/home/kilimanjaroo-picoctf/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
kilimanjaroo-picoctf@webshell:~$ nano fixme2.py 
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + chr(0x09) >

  
flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag == "":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)
kilimanjaroo-picoctf@webshell:~$ python3 fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}

## Notas Adicionales 
comando          descripción

## Referencias