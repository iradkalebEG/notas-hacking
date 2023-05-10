# Need For Speed - picoCTF 2019

## Descripción
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed).
## Pistas
What is the final key?
## Solución
```bash
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ wget https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed
--2023-05-09 20:07:27--  https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8888 (8.7K) [application/octet-stream]
Saving to: ‘need-for-speed’

need-for-speed                            100%[====================================================================================>]   8.68K  --.-KB/s    in 0s      

2023-05-09 20:07:36 (118 MB/s) - ‘need-for-speed’ saved [8888/8888]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ chmod +x need-for-speed
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ ls la 
ls: cannot access 'la': No such file or directory
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ ls -la
total 56
drwxr-xr-x 2 kali kali 4096 May  9 20:07 .
drwxr-xr-x 5 kali kali 4096 May  4 00:23 ..
-rw-r--r-- 1 kali kali 1447 May  2 17:49 bandera
-rwxr-xr-x 1 kali kali 8888 Oct 26  2020 need-for-speed
-rw-r--r-- 1 kali kali  756 May  9 17:50 test.S
-rw-r--r-- 1 kali kali  661 May  9 18:30 test.S.1
-rw-r--r-- 1 kali kali  286 Oct 26  2020 test.S.2
-rw-r--r-- 1 kali kali  320 May  4 15:22 test.S.2.save
-rw-r--r-- 1 kali kali 2264 Oct 26  2020 VaultDoor1.java
-rw-r--r-- 1 kali kali 1474 Oct 26  2020 VaultDoor3.java
-rw-r--r-- 1 kali kali 1497 Oct 26  2020 VaultDoor4.java
-rw-r--r-- 1 kali kali  943 Oct 26  2020 VaultDoorTraining.java
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ gbd need-for-speed 
Command 'gbd' not found, did you mean:
  command 'gsd' from deb python3-gsd
  command 'gdb' from deb gdb
  command 'gdb' from deb gdb-minimal
  command 'god' from deb ruby-god
  command 'gbp' from deb git-buildpackage
  command 'lbd' from deb lbd
  command 'sbd' from deb sbd
  command 'gid' from deb id-utils
  command 'rbd' from deb ceph-common
  command 'gzbd' from deb zbd-utils
  command 'gld' from deb postfix-gld
  command 'dbd' from deb dbd
  command 'bd' from deb bd
  command 'zbd' from deb zbd-utils
Try: sudo apt install <deb name>
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/reversing]
└─$ gdb need-for-speed
GNU gdb (Debian 13.1-2) 13.1
Copyright (C) 2023 Free Software Foundation, Inc.
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
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb) break main
Breakpoint 1 at 0x91e
(gdb) run
Starting program: /home/kali/Documents/reversing/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055555540091e in main ()
(gdb) x/32i get_key

   0x55555540087d <get_key>:    push   %rbp
   0x55555540087e <get_key+1>:  mov    %rsp,%rbp
   0x555555400881 <get_key+4>:  lea    0x1a0(%rip),%rdi        # 0x555555400a28
   0x555555400888 <get_key+11>: call   0x555555400610 <puts@plt>
   0x55555540088d <get_key+16>: mov    $0x0,%eax
   0x555555400892 <get_key+21>: call   0x5555554007f1 <calculate_key>
   0x555555400897 <get_key+26>: mov    %eax,0x2007bf(%rip)        # 0x55555560105c <key>
   0x55555540089d <get_key+32>: lea    0x194(%rip),%rdi        # 0x555555400a38
   0x5555554008a4 <get_key+39>: call   0x555555400610 <puts@plt>
   0x5555554008a9 <get_key+44>: nop
   0x5555554008aa <get_key+45>: pop    %rbp
   0x5555554008ab <get_key+46>: ret
   0x5555554008ac <print_flag>: push   %rbp
   0x5555554008ad <print_flag+1>:       mov    %rsp,%rbp
   0x5555554008b0 <print_flag+4>:       lea    0x18a(%rip),%rdi        # 0x555555400a41
   0x5555554008b7 <print_flag+11>:      call   0x555555400610 <puts@plt>
   0x5555554008bc <print_flag+16>:      mov    0x20079a(%rip),%eax        # 0x55555560105c <key>
   0x5555554008c2 <print_flag+22>:      mov    %eax,%edi
   0x5555554008c4 <print_flag+24>:      call   0x55555540076a <decrypt_flag>
   0x5555554008c9 <print_flag+29>:      lea    0x200750(%rip),%rdi        # 0x555555601020 <flag>
   0x5555554008d0 <print_flag+36>:      call   0x555555400610 <puts@plt>
   0x5555554008d5 <print_flag+41>:      nop
   0x5555554008d6 <print_flag+42>:      pop    %rbp
   0x5555554008d7 <print_flag+43>:      ret
   0x5555554008d8 <header>:     push   %rbp
   0x5555554008d9 <header+1>:   mov    %rsp,%rbp
   0x5555554008dc <header+4>:   sub    $0x10,%rsp
   0x5555554008e0 <header+8>:   lea    0x169(%rip),%rdi        # 0x555555400a50 <title>
   0x5555554008e7 <header+15>:  call   0x555555400610 <puts@plt>
   0x5555554008ec <header+20>:  movl   $0x0,-0x4(%rbp)
   0x5555554008f3 <header+27>:  jmp    0x555555400903 <header+43>
   0x5555554008f5 <header+29>:  mov    $0x3d,%edi
(gdb) 
   0x5555554008fa <header+34>:  call   0x555555400600 <putchar@plt>
   0x5555554008ff <header+39>:  addl   $0x1,-0x4(%rbp)
   0x555555400903 <header+43>:  mov    -0x4(%rbp),%eax
   0x555555400906 <header+46>:  cmp    $0x1b,%eax
   0x555555400909 <header+49>:  jbe    0x5555554008f5 <header+29>
   0x55555540090b <header+51>:  lea    0x15b(%rip),%rdi        # 0x555555400a6d
   0x555555400912 <header+58>:  call   0x555555400610 <puts@plt>
   0x555555400917 <header+63>:  nop
   0x555555400918 <header+64>:  leave
   0x555555400919 <header+65>:  ret
   0x55555540091a <main>:       push   %rbp
   0x55555540091b <main+1>:     mov    %rsp,%rbp
=> 0x55555540091e <main+4>:     sub    $0x10,%rsp
   0x555555400922 <main+8>:     mov    %edi,-0x4(%rbp)
   0x555555400925 <main+11>:    mov    %rsi,-0x10(%rbp)
   0x555555400929 <main+15>:    mov    $0x0,%eax
   0x55555540092e <main+20>:    call   0x5555554008d8 <header>
   0x555555400933 <main+25>:    mov    $0x0,%eax
   0x555555400938 <main+30>:    call   0x55555540082f <set_timer>
   0x55555540093d <main+35>:    mov    $0x0,%eax
   0x555555400942 <main+40>:    call   0x55555540087d <get_key>
   0x555555400947 <main+45>:    mov    $0x0,%eax
   0x55555540094c <main+50>:    call   0x5555554008ac <print_flag>
   0x555555400951 <main+55>:    mov    $0x0,%eax
   0x555555400956 <main+60>:    leave
   0x555555400957 <main+61>:    ret
   0x555555400958:      nopl   0x0(%rax,%rax,1)
   0x555555400960 <__libc_csu_init>:    push   %r15
   0x555555400962 <__libc_csu_init+2>:  push   %r14
   0x555555400964 <__libc_csu_init+4>:  mov    %rdx,%r15
   0x555555400967 <__libc_csu_init+7>:  push   %r13
   0x555555400969 <__libc_csu_init+9>:  push   %r12
(gdb) set 0x55555560105c=0x2007bf
Left operand of assignment is not an lvalue.
(gdb) set *0x55555560105c=0x2007bf
(gdb) call (int) print_flag()
Printing flag:
PICOCTF{Good job keeping bus #0b812872 speeding along!}
$1 = 56
(gdb)
```
## Bandera
picoCTF{Good job keeping bus #0b812872 speeding along!}

## Notas Adicionales 
comando          descripción

## Referencias