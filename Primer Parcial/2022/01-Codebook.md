# Codebook

## Descripción
Run the Python script `code.py` in the same directory as `codebook.txt`.

-   [Download code.py](https://artifacts.picoctf.net/c/1/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/1/codebook.txt)
## Pistas
On the webshell, use `ls` to see if both files are in the directory you are in.
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/1/code.py
--2023-03-17 18:24:09--  https://artifacts.picoctf.net/c/1/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                   100%[===================================================================================>]   1.25K  --.-KB/s    in 0s      

2023-03-17 18:24:09 (735 MB/s) - 'code.py' saved [1278/1278]

kilimanjaroo-picoctf@webshell:~$ ls
Addadshashanammu      README.txt  bandera.txt  ende.py  flag         ltdis.sh    lyrics.txt.1   pw.txt  static.ltdis.strings.txt  strings
Addadshashanammu.zip  bandera     code.py      file     flag.txt.en  lyrics.txt  nano.241.save  static  static.ltdis.x86_64.txt   warm
kilimanjaroo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/1/codebook.txt
--2023-03-17 18:24:31--  https://artifacts.picoctf.net/c/1/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.74, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                              100%[===================================================================================>]      27  --.-KB/s    in 0s      

2023-03-17 18:24:31 (12.2 MB/s) - 'codebook.txt' saved [27/27]

kilimanjaroo-picoctf@webshell:~$ python3 code.py 
picoCTF{c0d3b00k_455157_d9aa2df2}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{c0d3b00k_455157_d9aa2df2}

## Notas Adicionales 

## Referencias
