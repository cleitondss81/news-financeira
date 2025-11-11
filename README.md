# 📧 Newsletter Financeira Automatizada

Sistema automatizado de newsletter financeira que utiliza inteligência artificial (Agno AI) e pesquisa de notícias (Tavily) para criar e enviar newsletters diárias sobre o mercado financeiro brasileiro.

## 🚀 Funcionalidades

- **Pesquisa Automatizada**: Utiliza Tavily para buscar notícias financeiras de fontes confiáveis
- **Geração de Conteúdo**: Agno AI gera newsletters profissionais e estruturadas
- **Agendamento**: Sistema de agendamento para envio automático em horário específico
- **Envio por Email**: Envio automático via SMTP (Gmail)

## 📋 Pré-requisitos

- Python 3.12 ou superior
- Conta no OpenAI (para usar o modelo GPT)
- API Key do Tavily
- Conta Gmail com senha de app configurada

## 🔧 Instalação

1. Clone o repositório:
```bash
git clone https://github.com/cleitondss81/news-financeira.git
cd news-financeira
```

2. Instale as dependências usando `uv`:
```bash
uv sync
```

Ou usando `pip`:
```bash
pip install -r requirements.txt
```

## ⚙️ Configuração

1. Crie um arquivo `.env` na raiz do projeto:
```env
# OpenAI
OPENAI_API_KEY=sua_chave_openai

# Tavily (opcional, se necessário)
TAVILY_API_KEY=sua_chave_tavily

# Email
EMAIL_ADDRESS=seu_email@gmail.com
EMAIL_PASSWORD=sua_senha_de_app
DESTINATARIOS=destinatario1@email.com,destinatario2@email.com

# Agendamento (formato HH:MM)
SEND_AT=08:30
```

2. **Configuração do Gmail**:
   - Ative a verificação em duas etapas
   - Gere uma senha de app: [Google App Passwords](https://myaccount.google.com/apppasswords)
   - Use a senha de app no campo `EMAIL_PASSWORD`

## 🎯 Uso

### Execução Manual
```bash
python 03_news_financeira.py
```

### Execução com Agendamento
O script verifica automaticamente o horário configurado em `SEND_AT` e envia a newsletter no horário especificado.

## 📁 Estrutura do Projeto

```
news-financeira/
├── 03_news_financeira.py  # Script principal
├── prompt.py              # Prompt para o agente AI
├── pyproject.toml         # Dependências do projeto
├── .env                   # Variáveis de ambiente (não versionado)
└── README.md             # Este arquivo
```

## 🔍 Como Funciona

1. **Agendamento**: O script verifica continuamente se chegou o horário de envio
2. **Pesquisa**: Utiliza Tavily para buscar notícias financeiras recentes
3. **Geração**: Agno AI processa as notícias e gera uma newsletter estruturada
4. **Envio**: A newsletter é enviada automaticamente por email

## 📝 Formato da Newsletter

A newsletter inclui:
- Destaques do dia
- Análise do mercado de ações (Ibovespa)
- Mercado imobiliário
- Câmbio e economia
- Oportunidades da semana
- Dados importantes (Ibovespa, Dólar, CDI, IPCA)

## 🛠️ Tecnologias Utilizadas

- [Agno](https://github.com/agno-ai/agno) - Framework de agentes AI
- [OpenAI](https://openai.com/) - Modelo GPT-4.1-mini
- [Tavily](https://tavily.com/) - API de pesquisa de notícias
- Python 3.12+

## 📄 Licença

Este projeto é de código aberto e está disponível sob a licença MIT.

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests.

## ⚠️ Notas Importantes

- Certifique-se de manter suas chaves de API seguras (nunca as commite no repositório)
- O script roda em loop contínuo, então use com cuidado em produção
- Ajuste o intervalo de verificação (`time.sleep()`) conforme necessário

## 📧 Contato

Para dúvidas ou sugestões, abra uma issue no repositório.
