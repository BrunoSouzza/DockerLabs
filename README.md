# DotnetSQL + SQL Server Docker Example

Este projeto demonstra como subir uma aplicação .NET 8 com SQL Server usando Docker Compose, incluindo um exemplo de CRUD.

## Subindo o ambiente

1. **Pré-requisitos:**
   - Docker e Docker Compose instalados

2. **Suba os containers:**
   ```sh
   docker compose up --build
   ```

3. **Acesse o Swagger:**
   - [http://localhost:8080/swagger](http://localhost:8080/swagger)

## CRUD de Exemplo

- Endpoint: `/api/products`
- Métodos disponíveis:
  - `GET /api/products` (listar)
  - `GET /api/products/{id}` (detalhe)
  - `POST /api/products` (criar)
  - `PUT /api/products/{id}` (atualizar)
  - `DELETE /api/products/{id}` (remover)

## Observações
- O SQL Server é iniciado com usuário `sa` e senha `Your_password123`.
- O banco de dados padrão é `SampleDb`.
- A connection string está configurada em `appsettings.json` e no Docker Compose.

## Migrações
Se quiser criar a tabela automaticamente, rode:
```sh
dotnet ef migrations add InitialCreate --project DotnetSQL
```
Depois:
```sh
dotnet ef database update --project DotnetSQL
```

---

Qualquer dúvida, consulte o código ou peça ajuda!
