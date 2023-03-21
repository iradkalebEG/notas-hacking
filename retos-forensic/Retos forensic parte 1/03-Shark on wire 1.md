# Shark on wire 1

## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.
## Pistas
Try using a tool like Wireshark
What are streams?
## Solución
```bash
Hay que descargar el archivo que nos da el reto y abrirlo en un sistema operativo Linux para que nos lo abra con un explorador de archivos, en la barra que tiene para buscar ponemos este comando "udp.stream eq 6" pulsamos enter y nos llevara a un archivo, damos click derecho, follow, UDP Stream y encontraremos la bandera
```
## Bandera
picoCTF{StaT31355_636f6e6e}

## Notas Adicionales 

## Referencias