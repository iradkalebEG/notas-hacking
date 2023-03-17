# Python Wrangling

## Descripción
Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/ende.py) using [this password](https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/pw.txt) to get [the flag](https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/flag.txt.en)?
## Pistas
Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/5c4c0cbfbc149f3b0fc55c26f36ee707/ende.py`
`$ man python`
## Solución
```bash
kilimanjaroo-picoctf@webshell:~$ ls
README.txt  bandera  bandera.txt  ende.py  file  flag  flag.txt.en  lyrics.txt  lyrics.txt.1  nano.241.save  pw.txt  strings
kilimanjaroo-picoctf@webshell:~$ cat flag.txt.en 
gAAAAABgUAIVX7N_dNxY0j5lWtsDEN2b-h0mN-Lyhm_9QaEdwFK4em1kGiAV52ewbKv8wZJL2QwecZ7kTsVQ11PYEL3BJLD4LVyKrCKAvTFu5-1yuNGFAXKBY8GO3nIReXuOUbaSwVHlkilimanjaroo-picoctf@webshell:~$ cat pw.txt 
192ee2db192ee2db192ee2db192ee2db
kilimanjaroo-picoctf@webshell:~$ python3 ende.py -d flag.txt.en 
Please enter the password:192ee2db192ee2db192ee2db192ee2db
picoCTF{4p0110_1n_7h3_h0us3_192ee2db}
kilimanjaroo-picoctf@webshell:~$
```
## Bandera
picoCTF{4p0110_1n_7h3_h0us3_192ee2db}

## Notas Adicionales 
comando          descripción

## Referencias