# Vigenere

## Descripción
Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/160/cipher.txt) using this key "CYLAB".
## Pistas
https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher
## Solución
```bash
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ wget https://artifacts.picoctf.net/c/160/cipher.txt 
--2023-05-16 18:04:38--  https://artifacts.picoctf.net/c/160/cipher.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.74, 18.154.132.32, 18.154.132.88, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt           100%[===================>]      43  --.-KB/s    in 0s      

2023-05-16 18:04:39 (16.0 MB/s) - ‘cipher.txt’ saved [43/43]

                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ cat cipher.txt  
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}
                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ 

```
## Bandera
picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}

## Notas Adicionales 

## Referencias