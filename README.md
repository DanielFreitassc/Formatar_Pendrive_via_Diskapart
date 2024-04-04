# Formatar_Pendrive_via_Diskapart

# Abra o cmd e digite diskpart

# Liste os discos 
```
list disk
```
```
 Nº Disco  Status         Tam.     Livre    Din. GPT
  --------  -------------  -------  -------  ---  ---
  Disco 0    Online          931 GB      0 B
  Disco 1    Online          931 GB  1024 KB        *
  Disco 2    Online         7632 MB      0 B
```
# Selecione o disco que você deseja formatar
```
select disk 2
```
# Limpe
```
clean
```
# Liste as partições do disco
```
list partition
```
```
  Partição No.   Tipo              Tamanho  Deslocamento
  -------------  ----------------  -------  ------------
  Partição 1    Primário          7631 MB  1024 KB
```

# Selecione a partição desejada
```
select partition 1
```

# Ecolha um dos formatos abaixo e Formate a partição 

### FAT32
```
 format fs=FAT32 quick
```

### NTFS
```
format fs=NTFS quick
```

### exFAT
```
format fs=exFAT quick
```

# Em seguida atribua
```
assign
````

# Pronto digite exit para sair
```
exit
```
