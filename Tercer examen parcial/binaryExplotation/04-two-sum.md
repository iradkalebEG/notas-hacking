# two-sum

## Descripción
Can you solve this? What two positive numbers can make this possible: `n1 > n1 + n2 OR n2 > n1 + n2` Enter them here `nc saturn.picoctf.net 62863`. [Source](https://artifacts.picoctf.net/c/456/flag.c)
## Pistas

## Solución
```bash
──(kali㉿kali)-[~/Documents/reversing]
└─$ wget https://artifacts.picoctf.net/c/456/flag.c    
--2023-05-16 18:40:20--  https://artifacts.picoctf.net/c/456/flag.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.88, 18.154.132.74, 18.154.132.32, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1346 (1.3K) [application/octet-stream]
Saving to: ‘flag.c’

flag.c               100%[===================>]   1.31K  --.-KB/s    in 0s      

2023-05-16 18:40:21 (32.0 MB/s) - ‘flag.c’ saved [1346/1346]

                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ nc nc saturn.picoctf.net 62863
nc: forward host lookup failed: No address associated with name
                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ nc saturn.picoctf.net 62863 
n1 > n1 + n2 OR n2 > n1 + n2 
What two positive numbers can make this possible: 

^Q
                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ bc
Command 'bc' not found, but can be installed with:
sudo apt install bc
Do you want to install it? (N/y)y
sudo apt install bc
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  catfish dh-elpa-helper docutils-common gir1.2-xfconf-0 libcfitsio9 libgdal31
  libmpdec3 libnginx-mod-http-geoip libnginx-mod-http-image-filter
  libnginx-mod-http-xslt-filter libnginx-mod-mail libnginx-mod-stream
  libnginx-mod-stream-geoip libpoppler123 libprotobuf23 libpython3.10
  libpython3.10-dev libpython3.10-minimal libpython3.10-stdlib libtiff5
  libzxingcore1 nginx-common nginx-core python-pastedeploy-tpl
  python3-alabaster python3-commonmark python3-docutils python3-imagesize
  python3-roman python3-snowballstemmer python3-speaklater python3-sphinx
  python3.10 python3.10-dev python3.10-minimal ruby3.0 ruby3.0-dev ruby3.0-doc
  sphinx-common
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  bc
0 upgraded, 1 newly installed, 0 to remove and 501 not upgraded.
Need to get 110 kB of archives.
After this operation, 247 kB of additional disk space will be used.
Get:1 http://http.kali.org/kali kali-rolling/main amd64 bc amd64 1.07.1-3+b1 [110 kB]
Fetched 110 kB in 1s (121 kB/s)
Selecting previously unselected package bc.
(Reading database ... 422025 files and directories currently installed.)
Preparing to unpack .../bc_1.07.1-3+b1_amd64.deb ...
Unpacking bc (1.07.1-3+b1) ...
Setting up bc (1.07.1-3+b1) ...
Processing triggers for kali-menu (2023.1.5) ...
Processing triggers for doc-base (0.11.1) ...
Processing 1 added doc-base file...
Processing triggers for man-db (2.11.2-1) ...
                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ bc
bc 1.07.1
Copyright 1991-1994, 1997, 1998, 2000, 2004, 2006, 2008, 2012-2017 Free Software Foundation, Inc.
This is free software with ABSOLUTELY NO WARRANTY.
For details type `warranty'. 
2^31
2147483648
q
0
^C
(interrupt) use quit to exit.
q
0
^C
(interrupt) use quit to exit.
^C
(interrupt) use quit to exit.
^C
(interrupt) use quit to exit.
quit
                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ nc saturn.picoctf.net 62863
n1 > n1 + n2 OR n2 > n1 + n2 
What two positive numbers can make this possible: 
2147483647
57
You entered 2147483647 and 57
You have an integer overflow
YOUR FLAG IS: picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_ccd078bd}

                                                                                 
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ 
```
## Bandera
picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_ccd078bd}

## Notas Adicionales 
comando          descripción

## Referencias