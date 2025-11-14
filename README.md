# TodoApi — Minimal ASP.NET Core To‑Do API

This is a minimal ASP.NET Core API for managing a to-do list. It was built from scratch to demonstrate a simple, clean implementation of a CRUD service using .NET 8. It uses an in-memory store, so it's ready to run without any external database setup.

Key ideas:

- Minimal API style (single-file Program / lightweight routing)
- In-memory persistence for quick experimentation
- Clear, tiny surface area you can swap to EF Core / a real database later

## What you'll find here

- Endpoints for creating, reading, updating and deleting to‑do items
- DTO mapping to keep the API surface clean
- A small, self-contained codebase you can extend for demos or exercises

## Getting Started

To run this project, navigate to the root directory and execute the following commands:

```bash
dotnet restore
dotnet run
```

Once the application is running, you can access the Swagger UI to interact with the API at:

[https://localhost:5001/swagger](https://localhost:5001/swagger)

That's it — you should be able to call the API from the browser, curl, or Postman.

## API endpoints

All routes are under the root shown by the running app. The main endpoints included:

- `GET    /todoitems` — list all to‑do items
- `GET    /todoitems/complete` — list items marked complete
- `GET    /todoitems/{id}` — fetch a single item by id
- `POST   /todoitems` — create a new item (send JSON body)
- `PUT    /todoitems/{id}` — update an existing item
- `DELETE /todoitems/{id}` — remove an item

Use the Swagger UI to see request/response shapes and try calls interactively.

## Project layout

- `Program.cs` — entry point and Minimal API route wiring
- `Todo.cs` — domain model for a to‑do item
- `TodoItemDTO.cs` — DTO used by the API
- `TodoDb.cs` — minimal in‑memory persistence layer (replaceable)
- `TodoApi.csproj` — project file
- `appsettings.json` — default config

## Notes and next steps

- Data is stored in memory and will reset when the app restarts — this is intended for demos and learning.
- To make this production-ready, swap the in‑memory store for a persistent database (EF Core + SQL Server/Postgres) and add authentication, validation and tests.
