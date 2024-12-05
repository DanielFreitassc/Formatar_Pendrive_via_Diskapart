
---

# **Repositório de Gerenciamento de Discos**

Este repositório é um guia para o gerenciamento de discos em diferentes sistemas operacionais. O objetivo é fornecer uma maneira prática e eficiente de lidar com discos, seja para manutenção, formatação ou recuperação de dispositivos.

## **Objetivo**

O repositório oferece tutoriais para administrar e reparar discos em sistemas Linux e Windows. Atualmente, o foco está na recuperação de pendrives e na formatação correta de discos, garantindo que o processo seja o mais simples e claro possível.

## **Guias Atuais**

### **1. Como Formatando um Pendrive no Windows com Diskpart**

Este guia detalha os passos para formatar um pendrive no Windows utilizando a ferramenta **Diskpart**, que é uma ferramenta de linha de comando poderosa para gerenciamento de discos no Windows. O tutorial cobre desde a seleção do disco até a formatação com o sistema de arquivos adequado (FAT32, exFAT, NTFS).

#### Passos do Guia:
- Abrir o **Prompt de Comando** como Administrador.
- Usar o **Diskpart** para selecionar o pendrive.
- Limpar o disco e criar uma nova partição.
- Formatá-lo com o sistema de arquivos desejado.

### **2. Como Reparar Pendrive no Linux com `lsblk`**

Neste guia, mostramos como reparar um pendrive corrompido no Linux utilizando o comando **`lsblk`**, que permite visualizar o layout dos discos e partições no sistema. O tutorial oferece soluções para limpar a tabela de partições, recriar partições e formatar o dispositivo corretamente.

#### Passos do Guia:
- Identificar o pendrive utilizando **`lsblk`**.
- Usar **`fdisk`** para criar uma nova tabela de partições.
- Limpar qualquer dado residual e formatar o dispositivo.
- Montar a partição para testar a recuperação.

---

## **Tecnologias Utilizadas**
- **Diskpart** (Windows): Utilitário de linha de comando do Windows para gerenciamento de discos.
- **lsblk, fdisk, mkfs** (Linux): Ferramentas padrão para gerenciamento e formatação de discos no Linux.

---

## **Conclusão**

Este repositório é uma fonte útil de informações para quem precisa realizar tarefas relacionadas ao gerenciamento de discos. Fique atento a novos tutoriais e recursos que serão adicionados à medida que o repositório evolui.

---
