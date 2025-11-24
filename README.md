# 🚀 Cadastro de Usuários - CRUD em Java com Spring Boot 3.x

## Descrição do Projeto

Este repositório contém a implementação de um serviço *backend* RESTful completo para a gestão de registros de usuários. O projeto foi desenvolvido em **Java** com o framework **Spring Boot 3.x**, seguindo um padrão de **Arquitetura de Camadas Simples** (Controller, Service e Repository), o que garante código limpo, modular e de fácil manutenção. O foco é demonstrar a proficiência em construir APIs escaláveis e bem estruturadas para o seu portfólio.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Java (JDK 17+)
* **Framework:** Spring Boot 3.x (Versão 3.5.0 utilizada no tutorial)
* **Gerenciador de Dependências:** Apache Maven
* **Banco de Dados:** H2 Database (Em memória, ideal para desenvolvimento e testes)
* **Acesso a Dados:** Spring Data JPA (Hibernate)
* **Utilitários:** Lombok (Redução de código boilerplate)
* **Web:** Spring Web (Construção da API REST)

## ✨ Funcionalidades (Endpoints)

O projeto expõe os seguintes endpoints para manipulação da entidade `Usuário`:

| Operação | HTTP Verbo | Endpoint | Parâmetros | Descrição |
| :--- | :--- | :--- | :--- | :--- |
| **C**reate | `POST` | `/usuario` | Body (JSON) | Cadastra um novo usuário no banco de dados. |
| **R**ead | `GET` | `/usuario` | Query Param `email` | Busca e retorna um usuário pelo seu e-mail. |
| **U**pdate | `PUT` | `/usuario` | Query Param `id` e Body (JSON) | Atualiza os dados de um usuário existente pelo ID. |
| **D**elete | `DELETE` | `/usuario` | Query Param `email` | Remove o registro de um usuário pelo seu e-mail. |

A URL base para os endpoints é configurada como `http://localhost:8081/usuario` (a porta pode ser 8080 ou 8081, conforme configurado em `application.properties`).

## 📌 Destaques da Implementação

* **Arquitetura de Camadas:** Separação clara de responsabilidades entre as camadas de Apresentação (`Controller`), Negócio (`Service`) e Persistência (`Repository`).
* **Tratamento de Dados no Update:** Implementação de lógica para atualização parcial (utilizando operador ternário na camada de `Service` conforme o tutorial [00:20:37]), garantindo que dados não fornecidos no *payload* `PUT` não sejam perdidos, sendo preenchidos com os valores já existentes no banco.
* **Prevenção de Erros:** Uso do tipo `Optional` no `Repository` para forçar o tratamento de valores nulos e lançamento de exceções personalizadas (`RuntimeException` no exemplo) quando um registro não é encontrado [00:15:01].
* **JPA Customizado:** Criação de métodos customizados no `Repository`, como `findByEmail`, para buscas baseadas em atributos não-ID.

## ⚙️ Como Rodar o Projeto Localmente

1.  **Clone o Repositório:**
    ```bash
    git clone [https://docs.github.com/pt/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github](https://docs.github.com/pt/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github)
    cd nome-do-projeto
    ```
2.  **Configuração do Ambiente:** Certifique-se de ter o **Java JDK 17+** e o **Maven** instalados e configurados.
3.  **Execução:**
    Utilize o *wrapper* Maven para iniciar a aplicação:
    ```bash
    ./mvnw spring-boot:run
    ```
4.  **Acesso ao H2 Console:**
    Com a aplicação rodando (padrão na porta 8081), você pode acessar o console do banco de dados em memória para visualizar as tabelas:
    `http://localhost:8081/h2-console`

---

## 👨‍💻 Contribuidor

**[Seu nome/Nick do GitHub]** - Desenvolvedor Backend

*Este projeto foi desenvolvido seguindo o passo a passo do canal Javanauta no YouTube.*
[Assista ao tutorial aqui!](http://www.youtube.com/watch?v=yW7RrWfUeHE)
