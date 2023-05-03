# Pixelated

## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)
## Pistas
[https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
Think of different ways you can "stack" images
## Solución
```bash
(kali㉿kali)-[~/Documents/crypto]
└─$ wget https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png            
--2023-05-02 19:08:27--  https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197173 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png                                  100%[======================================================================================================>] 192.55K   846KB/s    in 0.2s    

2023-05-02 19:08:36 (846 KB/s) - ‘scrambled1.png’ saved [197173/197173]

                                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ wget https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png
--2023-05-02 19:09:04--  https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197172 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png                                  100%[======================================================================================================>] 192.55K   840KB/s    in 0.2s    

2023-05-02 19:09:12 (840 KB/s) - ‘scrambled2.png’ saved [197172/197172]

                                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/crypto]
└─$nano exp.py   
from PIL import Image
import numpy as np

imagen1 = np.asarray( Image.open('scrambled1.png'))
imagen2 = np.asarray( Image.open('scrambled2.png'))

print(imagen1)
print(imagen2)

datos= imagen1.copy() + imagen2.copy()

nueva= Image.fromarray(datos)

nueva.save('nueva.png', 'PNG')
                                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ python3 exp.py 
[[[ 84 183   4]
  [156  62  39]
  [122 202  87]
  ...
  [109  23  70]
  [ 16  42 114]
  [253 233 201]]

 [[120 171  36]
  [203   5   7]
  [ 51 194 163]
  ...
  [ 18  79  80]
  [ 77 181 216]
  [ 36 215 193]]

 [[ 42 157  55]
  [102 129  46]
  [206  37  55]
  ...
  [252 232 197]
  [106 140 221]
  [139 232 192]]

 ...

 [[200  34 241]
  [ 56 147  94]
  [ 89  45  44]
  ...
  [ 46  32 129]
  [ 29  88 171]
  [102 200 147]]

 [[ 34  44 255]
  [193 103  78]
  [246 247 147]
  ...
  [ 87 224  48]
  [101 155  18]
  [ 56 219  59]]

 [[122  58  52]
  [122 240  82]
  [ 86 130  84]
  ...
  [ 52 198  63]
  [231  94   1]
  [111 146   8]]]
[[[171  72 251]
  [ 99 193 216]
  [133  53 168]
  ...
  [146 232 185]
  [239 213 141]
  [  2  22  54]]

 [[135  84 219]
  [ 52 250 248]
  [204  61  92]
  ...
  [237 176 175]
  [178  74  39]
  [219  40  62]]

 [[213  98 200]
  [153 126 209]
  [ 49 218 200]
  ...
  [  3  23  58]
  [149 115  34]
  [116  23  63]]

 ...

 [[ 55 221  14]
  [199 108 161]
  [166 210 211]
  ...
  [209 223 126]
  [226 167  84]
  [153  55 108]]

 [[221 211   0]
  [ 62 152 177]
  [  9   8 108]
  ...
  [168  31 207]
  [154 100 237]
  [199  36 196]]

 [[133 197 203]
  [133  15 173]
  [169 125 171]
  ...
  [203  57 192]
  [ 24 161 254]
  [144 109 247]]]
                                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ ls              
bandera  bandera.png  exp.py  nueva.png  scrambled1.png  scrambled2.png
                                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ open nueva.png
```
## Bandera
picoCTF{2a4d45c7}

## Notas Adicionales 
comando          descripción

## Referencias