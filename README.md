# 📧 Sistema de Envio de E-mails Personalizados

## 📖 Introdução

Este projeto realiza o envio automático de e-mails personalizados utilizando templates em HTML e informações armazenadas em um banco de dados **SQLite**.  
Foi projetado para campanhas de pesquisa ou comunicação em massa com clientes, de forma segura e organizada, em geração de emails automatizados em massa.

---

## 🛠 Sobre o Projeto

A estrutura do projeto está organizada da seguinte forma:

```brash
emails/ 
├── web/ 
│ └── site/ 
│ ├── email1.html # Template de e-mail HTML (opcional) 
│ ├── email2.html # Template principal utilizado no envio 
├── envio.py # Script principal de envio dos e-mails 
├── .env.example # Exemplo de variáveis de ambiente 
├── .gitignore # Ignora arquivos sensíveis 
└── README.md #Documentação do projeto

```
- **`envio.py`**: Script responsável por:
  - Carregar variáveis do `.env`;
  - Conectar ao banco de dados e consultar empresas e e-mails;
  - Ler e personalizar o template HTML com o nome da empresa;
  - Enviar e-mails utilizando protocolo **SMTP seguro (TLS)**;
  - Controle de tempo entre envios para evitar bloqueios.

- **`email[1 ou 2].html`**: Template HTML do e-mail, onde `[empresa_name]` é substituído dinamicamente pelo nome da empresa, podendo ser escolhido entre as duas opções.

- **`.env.example`**: Exemplo de configuração para as variáveis de ambiente.

---

## 📦 Dependências

As principais dependências para execução são:

```bash
pip install python-dotenv
```

Ou, se preferir adicionar mais segurança:

```bash
pip install python-dotenv
```

## 📚 Bibliotecas utilizadas no projeto:

smtplib (nativo)

email.mime (nativo)

sqlite3 (nativo)

time (nativo)

os (nativo)

dotenv

## ⚙️ Variáveis de Ambiente (.env)
Crie um arquivo .env na raiz do projeto com o seguinte conteúdo:

*.env*

```
EMAIL_SENDER=seuemail@dominio.com
EMAIL_PASSWORD=sua_senha
SMTP_SERVER=smtp.dominio.com
SMTP_PORT=587
DB_PATH=caminho/para/seu/banco_de_dados.db
```
# ⚠️Importante:

Utilize servidores SMTP confiáveis.

Nunca versionar o .env para garantir segurança.

## 🚀 Como Executar
Clone o repositório:

```bash
git clone https://github.com/dreyvinixz/emails-automatisch-verschieben.git
```

Instale as dependências necessárias:

``` bash
pip install python-dotenv
```

Configure seu arquivo .env corretamente.

Execute o script de envio:

```bash
python web/site/envio.py
```

## 📊 Fluxo de Funcionamento
Conecta ao banco de dados e consulta os e-mails e nomes das empresas;

Para cada entrada:

Substitui [empresa_name] no template HTML;

Gera também uma versão texto puro (plain text);

Envia o e-mail via SMTP;

Aguarda 5 segundos antes do próximo envio.

## 📈 Futuras Melhorias
Implementar envio assíncrono para acelerar processos;

Adicionar logs detalhados para controle de status de envio;

Criar sistema de retry automático em caso de falha de envio;

Implementar suporte a múltiplos templates de forma dinâmica.

## 📚 Licença
Este projeto é livre para uso acadêmico e profissional mediante créditos à autoria.
Contato para colaborações: [codetoday]

---