# AWS EC2 + Nginx Deployment

## 📌 Descrição
Deploy de servidor Ubuntu 22.04 na AWS EC2 com instalação e configuração do Nginx, utilizando acesso remoto via SSH e configuração de Security Group.

---

## 🏗️ Arquitetura Utilizada

- AWS EC2 (t2.micro - Free Tier)
- Ubuntu Server 22.04 LTS
- Security Group liberando:
  - Porta 22 (SSH)
  - Porta 80 (HTTP)
- Acesso via chave .pem
- Nginx instalado via apt

---

## 🚀 Passo a Passo Técnico

### 1. Conectar na instância

ssh -i aws-chave.pem ubuntu@IP_PUBLICO

### 2. Atualizar pacotes

sudo apt update

### 3. Instalar Nginx

sudo apt install nginx -y

### 4. Iniciar Nginx

sudo systemctl start nginx

### 5. Verificar status

sudo systemctl status nginx

---

## ✅ Resultado

Servidor web acessível publicamente via IP público da instância.
Página padrão do Nginx funcionando corretamente.

---

## 🎯 Objetivo do Projeto

Demonstrar habilidades em:
- Provisionamento de infraestrutura na AWS
- Conexão remota via SSH
- Configuração de servidor Linux
- Instalação e gerenciamento de serviços web
