# 🤖 Telegram IoT Automation Bot

Projeto de automação residencial utilizando Telegram, n8n e Home Assistant para comunicação bidirecional entre usuário e dispositivos inteligentes.

O sistema permite tanto o envio de notificações automáticas baseadas em eventos quanto o controle remoto de dispositivos via comandos enviados pelo Telegram.

A automação é orquestrada pelo n8n através de workflows integrando APIs REST, autenticação via Bearer Token e lógica orientada a eventos.

---

## 🧠 Arquitetura

Telegram → n8n → Home Assistant → Dispositivo/Automação

O Telegram envia comandos para o webhook do n8n, que interpreta a mensagem, executa a lógica do fluxo e chama a API do Home Assistant para realizar ações ou consultar estados.

Após a execução, o bot responde automaticamente no Telegram com o resultado da operação.

---

## ⚙️ Tecnologias

- n8n (workflow automation)
- Home Assistant (IoT controller)
- Telegram Bot API
- REST API
- Webhooks
- Docker
- Automação orientada a eventos

---

## 📲 Comandos disponíveis

/status  
/ligar luz  
/desligar luz  

---

## 🔧 Como funciona

1. O usuário envia um comando via Telegram
2. O bot recebe via webhook no n8n
3. O n8n processa o comando
4. Uma requisição HTTP é enviada ao Home Assistant
5. O dispositivo IoT executa a ação
6. O bot responde ao usuário

---

## 📦 Estrutura do projeto
telegram-iot-automation-bot/
├── README.md
├── .env.example
├── n8n/
│ └── workflow.json
├── docs/
├── examples/

---

## 🧪 Exemplo de uso

Usuário:
> /ligar luz

Resposta:
> 💡 Luz da sala ligada

---

## 🔐 Segurança

O bot valida o `chat_id` para garantir que apenas usuários autorizados possam executar comandos.

Crie um arquivo .env baseado no .env.example.

Exemplo:

TELEGRAM_BOT_TOKEN=YOUR_TELEGRAM_BOT_TOKEN
TELEGRAM_CHAT_ID=123456789
HOME_ASSISTANT_TOKEN=YOUR_HOME_ASSISTANT_TOKEN
HOME_ASSISTANT_URL=http://homeassistant:8123

---

## 🚀 Objetivo do projeto

O objetivo deste projeto foi estudar integração entre plataformas, automação orientada a eventos, workflows no n8n e comunicação entre APIs.

Embora o exemplo utilize automação residencial simples, a mesma arquitetura pode ser aplicada em:

- monitoramento de servidores
- alertas automatizados
- bots operacionais
- automação de processos
- integrações SaaS
- workflows com IA

---

## 🔥 Possíveis melhorias

- suporte a múltiplos dispositivos
- integração com WhatsApp
- dashboard web
- logs de comandos

---
## Observações

Os tokens e credenciais foram removidos do workflow por segurança.

O projeto foi desenvolvido localmente utilizando Docker containers para o n8n e Home Assistant.

---

## 📎 Autor

Projeto desenvolvido para fins de portfólio profissional.