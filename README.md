# KiteWeb Application

Esta é a aplicação KiteWeb, uma aplicação Spring Boot para gerenciar fornecedores e produtos.

## Pré-requisitos

- Java 17
- Maven
- Conta no Azure com Web App configurado
- Git

## Configuração

- Clone o repositório:

   ```sh
   git clone https://github.com/<seu-usuario>/<seu-repositorio>.git
   cd <seu-repositorio>


## Execuntando a Aplicação

1. Compile e execute a aplicação localmente:

  mvn clean install
  mvn spring-boot:run

2. Acesse a aplicação em http://localhost:8090.

## Testes
  Execute os testes com Maven:
  
  mvn test


## Pipeline de CI/CD

O repositório está configurado com GitHub Actions para CI/CD. A pipeline é acionada em cada push ou pull request para a branch main e executa as seguintes etapas:

Checkout do código
Configuração do JDK 17
Build com Maven
Execução dos testes
Deploy para Azure Web App

## Endpoints da API
GET /fornecedor/lista: Lista todos os fornecedores
POST /fornecedor/form: Adiciona um novo fornecedor
GET /produto/lista: Lista todos os produtos
POST /produto/form: Adiciona um novo produto

## Scripts JSON de Exemplo

Fornecedor
{
  "id": 1,
  "nome": "Fornecedor Exemplo",
  "enderecoURL": "http://exemplo.com",
  "contato": "contato@exemplo.com"
}

Produto
{
  "id": 1,
  "nome": "Produto Exemplo",
  "descricao": "Descrição do Produto Exemplo",
  "preco": 100.0
}
