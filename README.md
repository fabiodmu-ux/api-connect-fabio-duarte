# api-connect-fabio-duarte

## 🎯 Objetivo da API
Esta é uma API REST de gerenciamento de usuários desenvolvida como solução técnica para fins didáticos e avaliativos. O objetivo do projeto é consolidar conceitos fundamentais de desenvolvimento web, manipulação de protocolos e métodos HTTP (GET e POST), validação de payloads com JSON, tratamento de códigos de status (Status Codes) e testes práticos de integração utilizando clientes HTTP como o Postman.

A aplicação simula em memória (array dinâmico) as operações básicas de persistência, validação e busca de registros de usuários.

## 🚀 Tecnologias Utilizadas
* **Node.js** (Ambiente de execução JavaScript assíncrono)
* **Express** (Framework minimalista e flexível para rotas HTTP)
* **JavaScript (ES6+)** (Linguagem de programação principal)
* **Git & GitHub** (Controle de versão e hospedagem de código)

## 💻 Passo a Passo para Execução Local

Siga as instruções abaixo para clonar o repositório e executar o servidor em sua máquina local:

### 1. Pré-requisitos
Certifique-se de ter o **Node.js** (versão 18 ou superior) instalado em sua máquina.

### 2. Clonar o Repositório
Abra o seu terminal e execute o comando abaixo para clonar este projeto:
```bash
git clone https://github.com[SEU_USUARIO_DO_GITHUB]/api-connect-[seu-nome]-[seu-sobrenome].git
```

### 3. Entrar na Pasta do Projeto
```bash
cd api-connect-[seu-nome]-[seu-sobrenome]
```

### 4. Instalar as Dependências
Instale os pacotes necessários listados no `package.json` (a pasta `node_modules` será gerada localmente):
```bash
npm install
```

### 5. Iniciar o Servidor
Execute o comando abaixo para ligar o servidor da API:
```bash
node server.js
```
Se tudo estiver correto, você verá a mensagem no terminal:  
`🚀 API de Usuários rodando em http://localhost:3000`

---

## 🛣️ Listagem Estruturada dos Endpoints

Abaixo estão detalhados os endpoints disponíveis na aplicação e os formatos esperados para cada cenário de teste:

### 1. Cadastro de Usuário (Sucesso)
* **Rota:** `/usuarios`
* **Método:** `POST`
* **Descrição:** Cadastra um novo usuário caso os campos obrigatórios sejam fornecidos corretamente.
* **Status Code Esperado:** `201 Created`
* **Corpo da Requisição (JSON - Exemplo):**
  ```json
  {
    "nome": "Fábio Oliveira",
    "email": "fabio@email.com"
  }
  ```

### 2. Falha no Cadastro (Validação)
* **Rota:** `/usuarios`
* **Método:** `POST`
* **Descrição:** Retorna um erro caso o payload enviado não contenha o campo obrigatório `email`.
* **Status Code Esperado:** `400 Bad Request`
* **Corpo da Requisição (JSON - Exemplo):**
  ```json
  {
    "nome": "Fábio Oliveira"
  }
  ```

### 3. Listagem Geral de Usuários
* **Rota:** `/usuarios`
* **Método:** `GET`
* **Descrição:** Retorna uma lista contendo todos os usuários cadastrados e armazenados na estrutura de memória.
* **Status Code Esperado:** `200 OK`
* **Corpo da Requisição:** Nenhum (Vazio).

### 4. Busca por ID (Falha)
* **Rota:** `/usuarios/:id` (Exemplo testado: `/usuarios/999`)
* **Método:** `GET`
* **Descrição:** Tenta buscar um usuário por um identificador numérico único. Retorna uma mensagem amigável de erro caso o ID informado não conste na memória.
* **Status Code Esperado:** `404 Not Found`
* **Corpo da Requisição:** Nenhum (Vazio).
