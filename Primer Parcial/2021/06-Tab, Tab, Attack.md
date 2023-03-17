# Tab, Tab, Attack

## Descripción
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip)
## Pistas 
After unziping, this problem can be solved with 11 button-presses...(mostly Tab)...
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ ls
Addadshashanammu      bandera      file         ltdis.sh      nano.241.save  static.ltdis.strings.txt  warm
Addadshashanammu.zip  bandera.txt  flag         lyrics.txt    pw.txt         static.ltdis.x86_64.txt
kilimanjaroo-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
kilimanjaroo-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
kilimanjaroo-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}
kilimanjaroo-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$
```
## Bandera
picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}

## Notas Adicionales 
descargar el zip con 'wget'
descomprimirlo con unzip 
## Referencias