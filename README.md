# TodoApi

Minimal ASP.NET Core (Minimal API) To‑Do service for demos and learning.

Features

- Simple CRUD endpoints for to‑do items
- In‑memory storage (no database required)
- Swagger UI for interactive testing

Quick start

```bash
dotnet restore
dotnet run --project TodoApi
```

Open the Swagger UI at: https://localhost:5001/swagger

API endpoints

- GET /todoitems — list all items
- GET /todoitems/complete — list completed items
- GET /todoitems/{id} — get an item by id
- POST /todoitems — create an item (JSON body)
- PUT /todoitems/{id} — update an item
- DELETE /todoitems/{id} — delete an item

Project layout

- `Program.cs` — entry point and route wiring
- `Todo.cs` — domain model for a to‑do item
- `TodoItemDTO.cs` — DTO used by the API
- `TodoDb.cs` — simple in‑memory persistence layer
- `TodoApi.csproj` — project file

Notes

- Data is stored in memory and resets when the app restarts — intended for demos.
- To persist data, replace `TodoDb` with an EF Core DbContext and a database provider.
- Target framework: .NET 8.