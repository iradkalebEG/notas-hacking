# Descripcion
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:21939/](http://mercury.picoctf.net:21939/)


# Pistas
1. Maybe you have more than 2 choices
2. Check out tools like Burpsuite to modify your requests and look at the responses

# Solucion
```
Content-type
	text/html; charset=UTF-8
flag
	picoCTF{r3j3ct_th3_du4l1ty_6ef27873}

──(kali㉿kali)-[~]
└─$ curl -I http://mercury.picoctf.net:21939/index.php
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_6ef27873}


```

# Bandera
picoCTF{r3j3ct_th3_du4l1ty_6ef27873}

# Notas adicionales
Comando -> curl -I

Proxy: Intermediario entre una cosa y otra.
En programación ayuda a ocultar nuestra identidad.


# Referencias