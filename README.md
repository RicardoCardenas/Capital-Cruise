# Capital Cruise

Capital Cruise is a full-stack vehicle financing platform made of two main projects:

- A **backend API** built with Spring Boot for authentication, business rules, persistence, and documentation.
- A **web frontend** built with Vue 3 and Vite for the user experience, simulations, and customer management.

The platform is focused on helping users explore loan simulations, manage operations, and work with financing-related workflows in a modern and modular architecture.

## Project Structure

```text
.
|-- backend/        # Spring Boot API
`-- frontend-web/   # Vue 3 web application
```

## Technology Stack

### Frontend

- Vue 3
- Vue Router
- Vite
- JavaScript (ES modules)
- QR code libraries for sharing or visual utilities

### Backend

- Java 21
- Spring Boot 3
- Spring Web
- Spring Data JPA
- Spring Security
- Spring Validation
- Flyway for database migrations
- PostgreSQL in production/runtime
- H2 for testing and local development
- JWT for authentication
- SpringDoc OpenAPI for API documentation
- Lombok for boilerplate reduction

## Main Features

- User authentication and protected routes
- Client management
- Loan simulations and loan quote workflows
- Operation details and public sharing pages
- Modular separation between public, IAM, clients, loans, and vehicle-related areas
- REST API documentation and database migrations on the backend

## Backend Overview

The backend exposes the application services and handles the core domain logic. It is organized as a Spring Boot application with:

- REST endpoints for the frontend
- Security and JWT-based authentication
- JPA entities and repositories for persistence
- Flyway migrations for database versioning
- Environment-specific configuration files for development, production, and Supabase-related setups

Backend folder: [backend/](backend)

## Frontend Overview

The frontend is a single-page application built with Vue 3 and Vite. It is organized into feature-based folders, such as:

- `clients`
- `iam`
- `loans`
- `public`
- `shared`
- `vehicles`

Each area contains its own components, views, services, utilities, and models to keep the codebase maintainable and scalable.

Frontend folder: [frontend-web/](frontend-web)

## Requirements

- Node.js 22 or newer for the frontend
- Java 21 for the backend
- Maven for backend builds
- PostgreSQL if you want to run the backend against a real database

## Getting Started

### 1. Start the backend

```bash
cd backend
mvn spring-boot:run
```

By default, the backend reads its environment-specific properties from the files in `src/main/resources`.

### 2. Start the frontend

```bash
cd frontend-web
pnpm install
pnpm dev
```

The frontend uses Vite for local development and development-time hot reload.

## Build Commands

### Frontend

```bash
pnpm build
pnpm preview
```

### Backend

```bash
mvn test
mvn package
```

## Configuration Notes

- Backend environments are separated into development, production, test, and Supabase-related property files.
- The backend includes database migrations under `src/main/resources/db`.
- The frontend uses Vite configuration and can be deployed independently.

## Deployment

The repository is structured so both projects can be deployed independently:

- The backend can run as a Spring Boot service.
- The frontend can be deployed as a static web app or SPA.
