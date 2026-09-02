# Conversor Decimal para Binário — API

API REST desenvolvida em Node.js e Express que converte números decimais para binário, com testes automatizados, documentação via Swagger, e integração experimental com bancos de dados relacional (MySQL) e não-relacional (MongoDB), ambos containerizados com Docker.

## 🚀 Funcionalidades

- Conversão de número decimal para binário via endpoint REST
- Validação de entrada (retorna erro 400 para valores inválidos)
- Testes automatizados com Jest
- Documentação da API no padrão OpenAPI (Swagger)
- Integração experimental com MongoDB e MySQL, cada um rodando em container Docker
- Configuração de Jenkins para futura automação de testes (CI/CD)

## 🛠️ Tecnologias utilizadas

- **Node.js** + **Express** — servidor e rotas da API
- **Jest** — testes automatizados
- **Swagger (OpenAPI)** — documentação da API
- **MongoDB** e **MySQL** — persistência de dados (integrações separadas)
- **Docker** e **Docker Compose** — containerização dos bancos de dados
- **Jenkins** — automação (CI/CD)
- **dotenv** — gerenciamento seguro de variáveis de ambiente

## 📁 Estrutura do projeto

```
TProgramacao/
├── app.js                 # API principal (lógica da conversão)
├── index.js                # Inicialização do servidor
├── app.test.js              # Testes automatizados (Jest)
├── validateDecimal.js       # Middleware de validação (em desenvolvimento)
├── documentacao.yml         # Documentação Swagger/OpenAPI
├── mongo-node/               # Versão da API integrada com MongoDB
├── mysql-node/                # Versão da API integrada com MySQL
└── jenkins/                    # Configuração do Jenkins via Docker
```

## ▶️ Como rodar o projeto

### API principal (sem banco de dados)

```bash
npm install
node index.js
```

Acesse: `http://localhost:3000/to-binary/10`

### Rodando os testes

```bash
npm test
```

### Versão com MongoDB

```bash
cd mongo-node
cp .env.example .env    # preencha com suas próprias credenciais
npm install
docker compose up -d
node index.js
```

### Versão com MySQL

```bash
cd mysql-node
cp .env.example .env    # preencha com suas próprias credenciais
npm install
docker compose up -d
node index.js
```

## 📌 Exemplo de uso

**Requisição:**
```
GET /to-binary/10
```

**Resposta:**
```json
{
  "decimal": 10,
  "binary": "1010"
}
```

## 🎓 Sobre este projeto

Este projeto foi desenvolvido como estudo prático durante o curso de Análise e Desenvolvimento de Sistemas, explorando desde os fundamentos de uma API REST até práticas de mercado como testes automatizados, documentação, containerização e cuidados de segurança (uso de variáveis de ambiente para credenciais).

## 👤 Autor

Vitor Enrique Rodrigues Rivero
[LinkedIn](https://www.linkedin.com/in/vitor-rivero-b2568014b/) · [GitHub](https://github.com/DEV-Shien)