# GDB baby step 1

## Descripción
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).
## Pistas
gdb is a very good debugger to use for this problem and many others!
`main` is actually a recognized symbol that can be used with gdb commands.
## Solución
```bash
┌──(kali㉿kali)-[~/…/notas-hacking/Utils/Tercer-Parcial/Reversing]
└─$ chmod +x debugger0_a        
                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/notas-hacking/Utils/Tercer-Parcial/Reversing]
└─$ ./debugger0_a 
                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/…/notas-hacking/Utils/Tercer-Parcial/Reversing]
└─$ gdb debugger0_a 
GNU gdb (Debian 12.1-4+b1) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
(gdb) layout asm
```
## Bandera
picoCTF{549698}

## Notas Adicionales 


## Referencias