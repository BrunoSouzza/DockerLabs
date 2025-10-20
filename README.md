# ⚠️ Aviso Importante

> Este projeto **não é uma aplicação completa**, mas sim um **ambiente pré-configurado** (assert) para uso com **Docker e SQL Server**, servindo como base para estudos, testes ou inicialização de novos projetos .NET com banco SQL Server.

---

# DotnetSQL + SQL Server Docker Example

Este projeto demonstra como subir uma aplicação **.NET 8** integrada com **SQL Server** usando **Docker Compose**, incluindo um exemplo simples de CRUD com **Entity Framework Core**.

---

## 🚀 Subindo o ambiente

1. **Pré-requisitos:**

   * Docker e Docker Compose instalados

2. **Suba os containers:**

   ```bash
   docker compose up --build
   ```

3. **Acesse o Swagger:**

   * [http://localhost:8080/swagger](http://localhost:8080/swagger)

---

## 🧩 CRUD de Exemplo

* **Endpoint base:** `/api/products`
* **Métodos disponíveis:**

  * `GET /api/products` → listar produtos
  * `GET /api/products/{id}` → detalhar produto
  * `POST /api/products` → criar produto
  * `PUT /api/products/{id}` → atualizar produto
  * `DELETE /api/products/{id}` → remover produto

---

## 🗄️ Criação Automática do Banco de Dados

O projeto utiliza **Entity Framework Core Migrations** para automatizar a criação e atualização do banco de dados.

Durante o processo de inicialização do container da aplicação (`docker compose up --build`):

* O **EF Core** é executado para aplicar as **migrations** existentes.
* Se o banco ainda não existir, ele será **criado automaticamente** dentro do container SQL Server.
* Essa abordagem elimina a necessidade de executar manualmente `dotnet ef database update`.

> 🔧 Caso novas entidades ou alterações sejam adicionadas ao modelo, basta gerar novas migrations com:
>
> ```bash
> dotnet ef migrations add NomeDaMigration
> ```
>
> E, em seguida, reconstruir o ambiente com:
>
> ```bash
> docker compose up --build
> ```

---

## ⚙️ Configurações

* SQL Server sobe com:

  * Usuário: `sa`
  * Senha: `Caracol@159`
* Banco de dados padrão: `SampleDb`
* Connection strings definidas em:

  * `appsettings.json`
  * `docker-compose.yml`
