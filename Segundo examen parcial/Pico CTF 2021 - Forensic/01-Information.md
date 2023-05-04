# Information

## Descripción
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg)
## Pistas
Look at the details of the file
Make sure to submit the flag as picoCTF{XXXXX}
## Solución
```bash
(kali㉿kali)-[~/Documents/forensic]
└─$ wget https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg
--2023-05-04 00:23:21--  https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 878136 (858K) [application/octet-stream]
Saving to: ‘cat.jpg’

cat.jpg                                   100%[====================================================================================>] 857.55K  1.42MB/s    in 0.6s    

2023-05-04 00:23:23 (1.42 MB/s) - ‘cat.jpg’ saved [878136/878136]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/forensic]
└─$ exiftool cat.jpg 
ExifTool Version Number         : 12.57
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 14:24:46-04:00
File Access Date/Time           : 2023:05:04 00:23:23-04:00
File Inode Change Date/Time     : 2023:05:04 00:23:23-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/forensic]
└─$ exiftool cat.jpg | grep License | sed -e 's/.*: //' | base64 -d
picoCTF{the_m3tadata_1s_modified}                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/forensic]
└─$
```
## Bandera
picoCTF{the_m3tadata_1s_modified}

## Notas Adicionales 
comando          descripción

## Referencias