# Fixme1.py

## Descripción
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/26/fixme1.py)
## Pistas
Indentation is very meaningful in Python
To view the file in the webshell, do: `$ nano fixme1.py`
To exit `nano`, press Ctrl and x and follow the on-screen prompts.
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/26/fixme1.py
--2023-03-17 19:10:44--  https://artifacts.picoctf.net/c/26/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                                 100%[===================================================================================>]     837  --.-KB/s    in 0s      

2023-03-17 19:10:44 (410 MB/s) - 'fixme1.py' saved [837/837]

kilimanjaroo-picoctf@webshell:~$ nano fixme1.py 
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
        print(i)
    print("unindented")
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) >

  
flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)

kilimanjaroo-picoctf@webshell:~$ python3 fixme1.py 
1
2
3
4
5
0
1
2
3
4
5
0
1
2
3
4
5
0
1
2
3
4
5
0
1
2
3
4
unindented
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{1nd3nt1ty_cr1515_09ee727a}

## Notas Adicionales 
comando          descripción

## Referencias