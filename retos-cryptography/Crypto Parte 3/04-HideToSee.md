# HideToSee

## Descripción
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/237/atbash.jpg).
## Pistas
Download the image and try to extract it.
## Solución
```bash
(kali㉿kali)-[~/Documents/crypto]
└─$ wget https://artifacts.picoctf.net/c/237/atbash.jpg 
}--2023-05-02 21:18:28--  https://artifacts.picoctf.net/c/237/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.88, 18.154.132.108, 18.154.132.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51508 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                                      100%[======================================================================================================>]  50.30K  --.-KB/s    in 0.1s    

2023-05-02 21:18:37 (504 KB/s) - ‘atbash.jpg’ saved [51508/51508]

                                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ open atbash.jpg 
                                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ 
```
una vez abierta la imagen nos vamos al siguiente URL:
https://futureboy.us/stegano/decinput.html
Ponemos la imagen q bajamos y nos dará lo siguiente:
krxlXGU{zgyzhs_xizxp_05y2z65z}
Ahora nos vamos a la siguiente URL:
https://www.dcode.fr/atbash-cipher
y colocamos lo que nos salio y nos dará la respuesta:
picoCTF{atbash_crack_05b2a65a}

## Bandera
picoCTF{atbash_crack_05b2a65a}

## Notas Adicionales 
comando          descripción

## Referencias