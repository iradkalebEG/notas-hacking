# ReadMyCert

## Descripción
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/422/readmycert.csr).
## Pistas
Download the certificate signing request and try to read it.
## Solución
```bash
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ wget https://artifacts.picoctf.net/c/422/readmycert.csr
--2023-05-02 21:35:28--  https://artifacts.picoctf.net/c/422/readmycert.csr
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.74, 18.154.132.88, 18.154.132.32, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 997 [application/octet-stream]
Saving to: ‘readmycert.csr’

readmycert.csr                                  100%[======================================================================================================>]     997  --.-KB/s    in 0s      

2023-05-02 21:35:37 (8.94 MB/s) - ‘readmycert.csr’ saved [997/997]

                                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ cat readmycert.csr 
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF8zNzNi
NGFiMH0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAKr+AToJg/TVTvfd9XzYR0gC5TOXa2+T24gjE8n7SHqynuo0Zlfy
oCqZHkxLha4QZszow4M+klP9fe1hy90LAU2enQGELrF3OF5SbNIVnPq97qrSHNI7
D9faAdsBqvezCto1MuMrRD35gwhQPga3WobkMdbJdDwuBpem/Tl3ko3Y9sxq2nAF
cmMNPj40GLtCfW55O8Awn2uN5gGZe+Nw2ArU9AYFidPtFZjBovHv7BVJz5XlhRhu
oiBALZES9kgfOyiwZrcJYZCJh9cJz3d+n2roMyAYMM/VZIjl0aZqSdOPeGYzs3GP
p/jFku8KNBn+mjyyw0H1vRnrK1hkNKXrXOcCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAG0c6ed5
a5zHU5IeI1KBvhGa+zGlrbm4lGQnGoI8wwlr6VN6v07/BGpwWfhjJatAOQ3txT5O
xDrM5A8caxpgGUXmat+C/9XCSQgRA+JckSk3rd6Wz7rYRuKsnycHzVIwyvIgSdjM
5/RKRdYHyFqYHPo9Tf1fThbV0tyQ+kr0tmsO6ZuaKgyDSxtky4U51XzSByKygHOT
Oi+VkzWvn74aOgbelBFMz+3vxaRHW85pe93jN6Gvc+HwYzUFja/SZXaN95sNRhcq
20SbOmg4r2pHUg0Lfs/0EHqDSg6JtKItqZmQUNhUQ7jmL6PtUpQQlkwlfMmEijRn
vlIEqBAkSbo63XQ=
-----END CERTIFICATE REQUEST-----
                                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/crypto]
└─$ 

```
Despues noa vamos a la siguiente URL:
https://www.sslshopper.com/csr-decoder.html
ponemos lo que nos mostró una vez que lo descargamos
y en la parte de abajo autoomaticamente nos dara la respuesta
## Bandera
picoCTF{read_mycert_373b4ab0}

## Notas Adicionales 

## Referencias