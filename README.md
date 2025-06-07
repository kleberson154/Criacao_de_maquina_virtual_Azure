# ☁️ Criação e Configuração de Máquina Virtual no Microsoft Azure

Este repositório documenta o processo de **criação, configuração e acesso** a uma **máquina virtual (VM)** no **Microsoft Azure**, utilizando o portal web.

---

## 📌 Objetivo

Fornecer um guia prático e direto para criar uma VM Linux ou Windows no Azure, desde a configuração inicial até o acesso remoto e boas práticas.

---

## 🧰 Pré-requisitos

- Conta ativa no **Microsoft Azure**
- Acesso ao [Azure Portal](https://portal.azure.com)
- (Opcional) Cliente SSH (Linux/macOS) ou RDP (Windows)

---

## 🚀 Etapas para Criação da VM

### 1. Acessar o Portal

- Acesse: [https://portal.azure.com](https://portal.azure.com)
- Vá em **"Máquinas Virtuais"**
- Clique em **"+ Criar" > "Máquina virtual"**

---

### 2. Configurações Básicas

| Campo              | Valor Exemplo                |
|--------------------|------------------------------|
| Assinatura         | Visual Studio / Pay-As-You-Go |
| Grupo de Recursos  | `meu-grupo-vm`               |
| Nome da VM         | `vm-linux-teste`             |
| Região             | `Brazil South`               |
| Imagem             | Ubuntu 20.04 LTS / Windows Server 2022 |
| Tamanho            | `Standard B1s`               |
| Nome de usuário    | `azureuser`                  |
| Autenticação       | Chave SSH (Linux) ou Senha (Windows) |

> 💡 O Azure pode gerar a chave SSH para você, se necessário.

---

### 3. Configurações de Disco

- Tipo: **SSD padrão** (ou HDD para menor custo)
- Discos adicionais podem ser adicionados após a criação

---

### 4. Rede

- VNet/Sub-rede: configuradas automaticamente
- IP público: **Habilitado**
- Porta de entrada:
  - Linux: **SSH (22)**
  - Windows: **RDP (3389)**

---

### 5. Avançado (Opcional)

- Diagnóstico de inicialização
- Extensões da VM (monitoramento, agentes, etc.)
- Tags para organização

---

### 6. Revisar e Criar

- Revise as configurações
- Clique em **"Criar"**
- Aguarde o provisionamento (2–5 minutos)

---

## 🔐 Acesso à Máquina Virtual

### Linux (SSH)

```bash
ssh azureuser@<IP-PÚBLICO>
```
---

### Windows (RDP)

1. Abra o Conexão de Área de Trabalho Remota

2. Insira o IP da VM

3. Use as credenciais criadas

---

### 🧹 Pós-Criação

- Atualizar o sistema operacional
- Instalar pacotes necessários (Apache, NGINX, Docker etc.)
- Configurar regras de firewall (NSG)
- Criar snapshots/backups

---

### 🛑 Parar ou Excluir a VM

- No Portal do Azure:
  - Clique em sua VM
  - Parar: suspende a cobrança de uso
  - Excluir: remove permanentemente a VM

---

### 📎 Referências

Documentação oficial do Azure Virtual Machines -> https://learn.microsoft.com/azure/virtual-machines
