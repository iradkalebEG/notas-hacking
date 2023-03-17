# Static ain't always noise

## Descripción
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static)? This [BASH script](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh) might help!
## Pistas

## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static
--2023-03-07 18:46:53--  https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                           100%[==========================================================>]   8.18K  --.-KB/s    in 0s      

2023-03-07 18:46:53 (70.0 MB/s) - 'static' saved [8376/8376]

kilimanjaroo-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh
--2023-03-07 18:47:12--  https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                         100%[==========================================================>]     785  --.-KB/s    in 0s      

2023-03-07 18:47:12 (488 MB/s) - 'ltdis.sh' saved [785/785]

kilimanjaroo-picoctf@webshell:~$ ls -la
total 1164
drwxr-xr-x 4 kilimanjaroo-picoctf kilimanjaroo-picoctf   4096 Mar  7 18:47 .
drwxr-xr-x 3 root                 root                     34 Mar  2 18:36 ..
-rw------- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf   1328 Mar  7 18:23 .bash_history
-rw-r--r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    220 Mar  2 18:36 .bash_logout
-rw-r--r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf   3771 Mar  2 18:36 .bashrc
drwxrwxr-x 3 kilimanjaroo-picoctf kilimanjaroo-picoctf     19 Mar  6 03:42 .local
-rw-r--r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    807 Mar  2 18:36 .profile
-rw------- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf     82 Mar  7 17:53 .python_history
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    215 Mar  7 18:47 .wget-hsts
-rw-r--r-- 1 root                 root                   4443 Mar  7 18:26 README.txt
drwxrwxr-x 2 kilimanjaroo-picoctf kilimanjaroo-picoctf      6 Mar  6 04:04 bandera
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf 287346 Mar  6 04:05 bandera.txt
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf   1328 Mar 16  2021 ende.py
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf  14551 Oct 26  2020 file
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf     34 Mar 16  2021 flag
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    140 Mar 16  2021 flag.txt.en
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    785 Mar 16  2021 ltdis.sh
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    772 Oct 26  2020 lyrics.txt
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf    877 Oct 26  2020 lyrics.txt.1
-rw------- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf  14670 Mar  6 03:42 nano.241.save
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf     33 Mar 16  2021 pw.txt
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf   8376 Mar 16  2021 static
-rw-rw-r-- 1 kilimanjaroo-picoctf kilimanjaroo-picoctf 776032 Oct 26  2020 strings
-rwxrwxr-x 1 kilimanjaroo-picoctf kilimanjaroo-picoctf  10936 Mar 16  2021 warm
kilimanjaroo-picoctf@webshell:~$ chmod +x ltdis.sh 
kilimanjaroo-picoctf@webshell:~$ chmod +x static  
kilimanjaroo-picoctf@webshell:~$ cat ltdis.sh 
#!/bin/bash



echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by 
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
        echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

        echo "Ripping strings from binary with file offsets..."
        strings -a -t x $1 > $1.ltdis.strings.txt
        echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"



else
        echo "Disassembly failed!"
        echo "Usage: ltdis.sh <program-file>"
        echo "Bye!"
fi
kilimanjaroo-picoctf@webshell:~$ ./ltdis.sh static 
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
kilimanjaroo-picoctf@webshell:~$ ls
README.txt  bandera.txt  file  flag.txt.en  lyrics.txt    nano.241.save  static                    static.ltdis.x86_64.txt  warm
bandera     ende.py      flag  ltdis.sh     lyrics.txt.1  pw.txt         static.ltdis.strings.txt  strings
kilimanjaroo-picoctf@webshell:~$ cat static.ltdis.strings.txt | grep pico
   1020 picoCTF{d15a5m_t34s3r_f5aeda17}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{d15a5m_t34s3r_f5aeda17}

## Notas Adicionales 
comando          descripción

## Referencias