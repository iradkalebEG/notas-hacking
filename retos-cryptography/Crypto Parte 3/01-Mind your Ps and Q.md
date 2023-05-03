#  Mind your Ps and Q

## Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values)
## Pistas
Bits are expensive, I used only a little bit over 100 to save money
## Solución
```bash
kilimanjaroo-picoctf@webshell:~/criptography/cryptoParte3$ wget https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values
--2023-04-27 18:19:37--  https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 206 [application/octet-stream]
Saving to: 'values'

values                                    100%[===================================================================================>]     206  --.-KB/s    in 0s      

2023-04-27 18:19:37 (114 MB/s) - 'values' saved [206/206]

kilimanjaroo-picoctf@webshell:~/criptography/cryptoParte3$ cat values 
Decrypt my super sick RSA:
c: 964354128913912393938480857590969826308054462950561875638492039363373779803642185
n: 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
kilimanjaroo-picoctf@webshell:~/criptography/cryptoParte3$

C:\Users\ikale>python3
Python 3.11.3 (tags/v3.11.3:f3909b8, Apr  4 2023, 23:49:59) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()

C:\Users\ikale>python3
Python 3.11.3 (tags/v3.11.3:f3909b8, Apr  4 2023, 23:49:59) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> from Cryoto.Util.number import inverse, long_to_bytes
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'Cryoto'
>>> from Crypto.Util.number import inverse, long_to_bytes
>>> p = 2434792384523484381583634042478415057961
>>> q = 650809615742055581459820253356987396346063
>>> n = 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> p*q = n
  File "<stdin>", line 1
    p*q = n
    ^^^
SyntaxError: cannot assign to expression here. Maybe you meant '==' instead of '='?
>>> p*q == n
True
>>> e = 65537
>>> c = 964354128913912393938480857590969826308054462950561875638492039363373779803642185
>>> tn = (p-1) * (q-1)
>>> d = inverse(e, tn)
>>> m = pow(c,d,n)
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_73918962}'
>>>
```
## Bandera
picoCTF{sma11_N_n0_g0od_73918962}

## Notas Adicionales 

## Referencias