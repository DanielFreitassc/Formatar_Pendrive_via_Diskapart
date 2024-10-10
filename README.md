# Formatar_Pendrive_via_Diskapart

# Abra o cmd e digite 
```yml
diskpart
```
# Liste os discos 

```yml
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
```yml
select disk 2
```
# Limpe
```yml
clean
```
# Crie partição
```yml
create partition primary
```

# Liste as partições do disco
```yml
list partition
```
```yml
  Partição No.   Tipo              Tamanho  Deslocamento
  -------------  ----------------  -------  ------------
  Partição 1    Primário          7631 MB  1024 KB
```

# Selecione a partição desejada
```yml
select partition 1
```

# Ecolha um dos formatos abaixo e Formate a partição 

### FAT32
```yml
 format fs=FAT32 quick
```

### NTFS
```yml
format fs=NTFS quick
```

### exFAT
```yml
format fs=exFAT quick
```

# Em seguida atribua
```yml
assign
````

# Pronto digite exit para sair
```
exit
```
