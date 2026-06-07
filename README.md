# 🌱 Plant Disease Bot MVP

Bot desenvolvido em **n8n** para identificação de doenças em plantas por meio de imagens enviadas via Telegram.

O projeto combina visão computacional, inteligência artificial e automação para fornecer diagnósticos preliminares de problemas fitossanitários de forma simples e acessível ao agricultor.

---

## 📋 Visão Geral

O fluxo recebe uma foto enviada pelo usuário no Telegram, valida se a imagem realmente contém uma planta e, em seguida, realiza uma análise utilizando a API Plant.id.

Após o diagnóstico, uma resposta amigável é gerada por IA e enviada ao usuário contendo:

- Problema identificado
- Nível de confiança da análise
- Explicação simplificada
- Possíveis causas
- Recomendações de tratamento
- Dicas de prevenção

---

## 🏗️ Arquitetura da Solução

```text
Usuário
   │
   ▼
Telegram Bot
   │
   ▼
Recebe Imagem
   │
   ▼
Validação da Imagem (OpenAI Vision)
   │
   ├── Não é planta
   │       ▼
   │   Mensagem orientativa
   │
   └── É planta
           ▼
     Plant.id API
           ▼
      Diagnóstico
           ▼
      OpenAI GPT
           ▼
   Resposta Humanizada
           ▼
      Telegram
```

---

## ⚙️ Tecnologias Utilizadas

- **n8n**
- **Telegram Bot API**
- **OpenAI GPT-4.1 Nano**
- **Plant.id API**
- JavaScript (nó Code)

---

## 🚀 Funcionalidades

### 📷 Recebimento de Imagens

O usuário envia uma foto diretamente pelo Telegram.

### 🌿 Validação da Imagem

Antes de consumir recursos da API de diagnóstico, uma análise por IA verifica se a imagem contém uma planta.

Caso a imagem não seja válida, o usuário recebe uma mensagem explicativa.

### 🔍 Diagnóstico Fitossanitário

A imagem é enviada para a API Plant.id, responsável pela identificação de doenças e problemas na planta.

### 🤖 Geração de Resposta Humanizada

Os dados técnicos retornados pela API são transformados em uma explicação clara e amigável utilizando OpenAI.

### 📲 Retorno Automático

O diagnóstico é enviado automaticamente ao usuário pelo Telegram.

---

## 📌 Fluxo do Workflow

### 1. Receber Mensagem

O workflow inicia através de um gatilho do Telegram.

### 2. Verificar se Existe Foto

Caso não exista imagem na mensagem:

- Solicita o envio de uma foto da planta.

### 3. Baixar Arquivo

Obtém a imagem enviada pelo usuário.

### 4. Converter para Base64

Prepara a imagem para processamento pelas APIs.

### 5. Validar Conteúdo da Imagem

Utiliza OpenAI Vision para determinar se a imagem contém uma planta.

### 6. Consultar Plant.id

Caso a imagem seja válida:

- Envia a foto para análise fitossanitária.

### 7. Gerar Explicação

Utiliza OpenAI para converter o resultado técnico em uma linguagem acessível.

### 8. Enviar Resposta

Retorna o diagnóstico ao usuário via Telegram.

---

## 💬 Exemplo de Resposta

```text
🌱 Diagnóstico

Problema identificado:
Ferrugem da folha

Confiança da análise:
94%

O que está acontecendo:
A planta apresenta sinais típicos de ferrugem, uma doença causada por fungos que afeta o desenvolvimento saudável das folhas.

Sinais visíveis:
- Manchas alaranjadas
- Descoloração das folhas
- Queda prematura

Por que isso acontece:
- Alta umidade
- Pouca circulação de ar

O que fazer agora:
- Remover folhas afetadas
- Aplicar fungicida adequado
- Melhorar ventilação da área

Como prevenir no futuro:
- Evitar excesso de irrigação
- Realizar inspeções frequentes
```

---

## 🔧 Configuração

### Pré-requisitos

- Instância do n8n
- Bot criado no Telegram
- Chave de API da Plant.id
- Credenciais OpenAI

### Importação

1. Abra o n8n.
2. Clique em **Import Workflow**.
3. Importe o arquivo JSON do projeto.
4. Configure as credenciais:
   - Telegram
   - OpenAI
   - Plant.id
5. Ative o workflow.

---

## 🔒 Segurança

Antes de publicar o workflow em ambientes públicos, remova:

- Credenciais
- Tokens
- Chaves de API
- Webhook IDs
- IDs internos do n8n
- Instance IDs

O arquivo disponibilizado neste repositório não deve conter informações sensíveis.

---

## 📈 Possíveis Evoluções

- Histórico de diagnósticos
- Banco de dados para consultas futuras
- Identificação da espécie da planta
- Suporte a múltiplas imagens
- Dashboard de monitoramento
- Integração com WhatsApp
- Recomendações específicas por cultura agrícola

---

## 🎯 Objetivo do Projeto

Este projeto foi desenvolvido como MVP (Minimum Viable Product) para demonstrar a aplicação de:

- Inteligência Artificial
- Visão Computacional
- Automação de Processos
- Integração de APIs
- Desenvolvimento Low-Code

em um cenário real do agronegócio.

---

## 👨‍💻 Autor

**Mateus Henrique**

Projeto desenvolvido para fins de estudo, demonstração técnica e portfólio profissional.
