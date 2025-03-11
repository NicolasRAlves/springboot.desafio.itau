# 📌 Documentação da API - Desafio Itaú

## 📖 Introdução

Esta API REST permite registrar transações, limpar registros e obter estatísticas das transações realizadas nos últimos 60 segundos. A aplicação foi desenvolvida em Java com Spring Boot e armazena os dados em memória, conforme as especificações do desafio.

## 🚀 Endpoints da API

### 1️⃣ Criar uma Transação

**POST /transacao**

**Descrição:** Registra uma nova transação.

**Request Body:**
```json
{
    "valor": 123.45,
    "dataHora": "2020-08-07T12:34:56.789-03:00"
}
```
- `valor`: Número decimal representando o valor da transação.
- `dataHora`: Data e hora da transação no formato ISO 8601.

**Restrições:**
- `valor` deve ser maior ou igual a 0.
- `dataHora` deve estar no passado (transações futuras são rejeitadas).

**Respostas:**
- `201 Created`: Transação registrada com sucesso.
- `400 Bad Request`: JSON inválido.
- `422 Unprocessable Entity`: Transação inválida (data futura ou valor negativo).

### 2️⃣ Apagar Todas as Transações

**DELETE /transacao**

**Descrição:** Remove todas as transações armazenadas.

**Respostas:**
- `200 OK`: Todas as transações foram apagadas com sucesso.

### 3️⃣ Obter Estatísticas das Transações

**GET /estatistica**

**Descrição:** Retorna estatísticas das transações dos últimos 60 segundos.

**Request Body:**
```json
{
    "count": 10,
    "sum": 1234.56,
    "avg": 123.456,
    "min": 12.34,
    "max": 123.56
}
```

**Respostas:**
- `200 OK`: Estatísticas calculadas com sucesso.
- Caso não haja transações, os valores retornados serão 0.

## 📌 Como Executar o Sistema

### 📂 1. Requisitos

Antes de executar a aplicação, certifique-se de ter instalado:

- Java 17+
- Maven 3+

### ⚙️ 2. Clonar o Repositório

Execute o comando para clonar o repositório e acessar o diretório do projeto.
```bash
git clone https://github.com/NicolasRAlves/springboot.desafio.itau
cd springboot.desafio.itau
```

### 🏗️ 3. Construir o Projeto

Compile e construa a aplicação com o Maven.
```bash
mvn clean install
```
### ▶️ 4. Executar a Aplicação

Inicie a API. Ela estará disponível em `http://localhost:8080`.
```bash
mvn spring-boot:run
```

### 🛠️ 5. Testando a API

Você pode testar os endpoints utilizando ferramentas como **Postman** ou **Thunder Client (VSCODE)**.

## 📌 Tecnologias Utilizadas

- Java 17
- Spring Boot 3
- Maven

## 📌 Considerações Finais

Este desafio foi uma ótima oportunidade para reforçar conceitos de API REST, Spring Boot, validação de dados e performance. O projeto segue boas práticas e está organizado para facilitar a compreensão e manutenção.




