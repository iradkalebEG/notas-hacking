# Secrets

## Descripción
We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:53932/).
## Pistas
folders folders folders
## Solución
Para este reto tenemos que abrir el link que nos da el reto, ver el codigo fuente
dar click en el archivo css:
[secret/assets/index.css](view-source:http://saturn.picoctf.net:53932/secret/assets/index.css)
borrar el URL hasta 'secret'
dar click en el archivo:
[hidden/file.css](view-source:http://saturn.picoctf.net:53932/secret/hidden/file.css)
borrar la siguiente parte del URL: 'file.css'
dar click en:
[superhidden/login.css](view-source:http://saturn.picoctf.net:53932/secret/hidden/superhidden/login.css)
borrar la siguiente parte del URL: 'login.css'
y al dar enter aparecera la bandera.
```bash

```
## Bandera
picoCTF{succ3ss_@h3n1c@10n_51b260fe}

## Notas Adicionales 
comando          descripción

## Referencias