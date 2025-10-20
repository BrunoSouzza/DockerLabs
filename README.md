# DotnetSQL + SQL Server Docker Example

Este projeto demonstra como subir uma aplica��o .NET 8 com SQL Server usando Docker Compose, incluindo um exemplo de CRUD.

## Subindo o ambiente

1. **Pr�-requisitos:**
   - Docker e Docker Compose instalados

2. **Suba os containers:**
   ```sh
   docker compose up --build
   ```

3. **Acesse o Swagger:**
   - [http://localhost:8080/swagger](http://localhost:8080/swagger)

## CRUD de Exemplo

- Endpoint: `/api/products`
- M�todos dispon�veis:
  - `GET /api/products` (listar)
  - `GET /api/products/{id}` (detalhe)
  - `POST /api/products` (criar)
  - `PUT /api/products/{id}` (atualizar)
  - `DELETE /api/products/{id}` (remover)

## Observa��es
- O SQL Server � iniciado com usu�rio `sa` e senha `Your_password123`.
- O banco de dados padr�o � `SampleDb`.
- A connection string est� configurada em `appsettings.json` e no Docker Compose.

## Migra��es
Se quiser criar a tabela automaticamente, rode:
```sh
dotnet ef migrations add InitialCreate --project DotnetSQL
```
Depois:
```sh
dotnet ef database update --project DotnetSQL
```

---

Qualquer d�vida, consulte o c�digo ou pe�a ajuda!
