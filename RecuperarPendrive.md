A---

# **Recuperação de Pendrive Corrompido no Linux**

Este guia documenta os passos realizados para corrigir um pendrive corrompido no Linux. Ele cobre desde a análise inicial até a recriação da tabela de partição e formatação.

## **1. Identificação do dispositivo**
Primeiro, identificamos o pendrive usando o comando `lsblk`:

```bash
lsblk
```

Saída inicial:
```
sda           8:0    1   7,5G  0 disk 
└─sda2        8:2    1   1,5G  0 part /media/dan/7A44-EA41
```

O dispositivo identificado foi **`/dev/sda`**.

---

## **2. Verificação da tabela de partição**
Ao abrir o `fdisk` para analisar o dispositivo, foi constatado que ele não continha uma tabela de partição válida.

Comando:
```bash
sudo fdisk /dev/sda
```

Saída:
```
A unidade não contém uma tabela de partição conhecida.
Criado um novo rótulo de disco DOS com o identificador de disco 0x87f99eff.
```

---

## **3. Criação de uma nova tabela de partição**
Dentro do `fdisk`, seguimos os passos abaixo:

1. Criar uma nova partição primária:
   - Digitar `n` e selecionar as opções padrão para tamanho.
   - Salvar as alterações com `w`.

Comando executado no `fdisk`:
```bash
n
w
```

Após isso, verificamos novamente a estrutura com `lsblk`:
```bash
lsblk
```

---

## **4. Limpeza completa da tabela de partição (opcional)**
Como o pendrive ainda apresentava partições extras e mensagens confusas, foi necessário limpar o início do disco:

```bash
sudo dd if=/dev/zero of=/dev/sda bs=512 count=1
```

Isso apagou completamente a tabela de partição, permitindo recriá-la do zero.

---

## **5. Recriação da tabela de partição**
Reabrimos o `fdisk` e criamos uma nova tabela de partição:

1. Criar uma nova tabela de partição DOS:
   ```bash
   o
   ```
2. Criar uma partição primária:
   ```bash
   n
   ```
3. Salvar as alterações:
   ```bash
   w
   ```

---

## **6. Formatação da partição**
Após criar a partição, formatamos com o sistema de arquivos FAT32 para máxima compatibilidade:

```bash
sudo mkfs.vfat -F 32 /dev/sda1
```

---

## **7. Montagem e teste**
Montamos a partição formatada para verificar se tudo estava funcionando corretamente:

```bash
sudo mount /dev/sda1 /mnt
ls /mnt
```

O diretório estava vazio, indicando que o pendrive estava funcional.

---

## **8. Desmontagem e conclusão**
Por fim, desmontamos o pendrive para finalização segura:

```bash
sudo umount /mnt
```

Agora, o pendrive está corrigido e pronto para uso!

---

## **Resumo de Comandos Utilizados**

1. Identificar o pendrive:
   ```bash
   lsblk
   ```

2. Abrir o `fdisk`:
   ```bash
   sudo fdisk /dev/sda
   ```

3. Limpar tabela de partição (opcional):
   ```bash
   sudo dd if=/dev/zero of=/dev/sda bs=512 count=1
   ```

4. Formatar a partição:
   ```bash
   sudo mkfs.vfat -F 32 /dev/sda1
   ```

5. Montar a partição:
   ```bash
   sudo mount /dev/sda1 /mnt
   ```

6. Desmontar:
   ```bash
   sudo umount /mnt
   ```

---

Essa documentação pode ser usada como referência para corrigir pendrives corrompidos no Linux.