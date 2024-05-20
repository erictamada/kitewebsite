# KiteWeb Application

Esta é a aplicação KiteWeb, uma aplicação Spring Boot para gerenciar fornecedores e produtos.

## Pré-requisitos

- Java 17
- Maven
- Conta no Azure com Web App configurado
- Git

## Configuração

- Clone o repositório:

   git clone https://github.com/erictamada/kitewebsite.git
   cd kitewebsite


## Execuntando a Aplicação

1. Compile e execute a aplicação localmente:

     mvn clean install
   
     mvn spring-boot:run

3. Acesse a aplicação em http://localhost:8090.

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


## Configuração do Ambiente

1.Checkout de Código

Utiliza a ação actions/checkout@v4 para clonar o repositório do GitHub no ambiente de execução


2.Set up Java version

Utiliza a ação actions/setup-java@v1 para configurar o ambiente com a versão do Java necessária (Java 17).


3. Build com Maven

Executa o comando mvn clean install para compilar o código e gerar o arquivo JAR.


4. Upload artifact

Usa a ação actions/upload-artifact@v3 para fazer upload do arquivo JAR gerado para ser usado na fase de deploy.


5. Download artifact

Utiliza a ação actions/download-artifact@v3 para baixar o artefato JAR gerado na fase de build.


6. Login no Azure

Utiliza a ação azure/login@v1 para autenticar no Azure com as credenciais armazenadas nos GitHub Secrets.


7. Deploy para Azure Web App

Usa a ação azure/webapps-deploy@v2 para implantar o artefato JAR no Azure Web App.


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
