# Wave a Flag

## Descripción
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm) has extraordinarily helpful information...
## Pistas
This program will only work in the webshell or another Linux computer.
To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm`
Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
-h and --help are the most common arguments to give to programs to get more information from them!
Not every program implements help features like -h and --help.
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm
--2023-03-07 18:27:12--  https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                             100%[==========================================================>]  10.68K  --.-KB/s    in 0s      

2023-03-07 18:27:12 (338 MB/s) - 'warm' saved [10936/10936]

kilimanjaroo-picoctf@webshell:~$ chmod +x warm
kilimanjaroo-picoctf@webshell:~$ ls -la
total 1148
drwxr-xr-x 4 kilimanjaroo-picoctf kilimanjaroo-picoctf   4096 Mar  7 18:27 .
drwxr-xr-x 3 root                 root                     34 Mar  2 18:36 ..
-rw------- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf   1328 Mar  7 18:23 .bash_history
-rw-r--r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    220 Mar  2 18:36 .bash_logout
-rw-r--r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf   3771 Mar  2 18:36 .bashrc
drwxrwxr-x 3 kilimanjaroo-picoctf kilimanjaroo-picoctf     19 Mar  6 03:42 .local
-rw-r--r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    807 Mar  2 18:36 .profile
-rw------- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf     82 Mar  7 17:53 .python_history
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    215 Mar  7 18:27 .wget-hsts
-rw-r--r-- 1 root                 root                   4443 Mar  7 18:26 README.txt
drwxrwxr-x 2 kilimanjaroo-picoctf kilimanjaroo-picoctf      6 Mar  6 04:04 bandera
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf 287346 Mar  6 04:05 bandera.txt
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf   1328 Mar 16  2021 ende.py
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf  14551 Oct 26  2020 file
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf     34 Mar 16  2021 flag
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    140 Mar 16  2021 flag.txt.en
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    772 Oct 26  2020 lyrics.txt
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    877 Oct 26  2020 lyrics.txt.1
-rw------- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf  14670 Mar  6 03:42 nano.241.save
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf     33 Mar 16  2021 pw.txt
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf 776032 Oct 26  2020 strings
-rwxrwxr-x 1 kilimanjaroo-picoctf kilimanjaroo-picoctf  10936 Mar 16  2021 warm
kilimanjaroo-picoctf@webshell:~$ ./warm 
Hello user! Pass me a -h to learn what I can do!
kilimanjaroo-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_616f7182}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{b1scu1ts_4nd_gr4vy_616f7182}

## Notas Adicionales 
comando          descripción

## Referencias