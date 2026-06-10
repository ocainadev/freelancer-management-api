# DevFreela API

DevFreela is a freelance project management API built with ASP.NET Core, following Clean Architecture principles and modern backend development practices.

The application allows clients and freelancers to manage projects, comments, and user accounts while providing authentication and authorization through JWT tokens.

## Overview

The project was developed to demonstrate advanced backend concepts commonly used in enterprise applications, including:

* Clean Architecture
* CQRS
* MediatR
* Entity Framework Core
* JWT Authentication
* Role-Based Authorization
* Unit Testing
* Repository Pattern

## Features

### User Management

* User registration
* User authentication
* JWT token generation
* User listing and retrieval

### Project Management

* Create projects
* Update projects
* Delete projects
* Start projects
* Complete projects
* List projects
* View project details

### Comments

* Add comments to projects

### Security

* JWT Authentication
* Protected endpoints
* Role-based authorization
* Client and Freelancer roles

## Tech Stack

### Backend

* C#
* .NET 8
* ASP.NET Core Web API

### Architecture

* Clean Architecture
* CQRS
* MediatR
* Repository Pattern

### Data Access

* Entity Framework Core
* SQL Server

### Security

* JWT Bearer Authentication
* ASP.NET Identity Concepts

### Testing

* xUnit

## Architecture

The solution is organized into multiple layers:

```text
DevFreela.API
│
├── Controllers
├── Authentication
├── Exception Handling
│
DevFreela.Application
│
├── Commands
├── Queries
├── Handlers
├── Validators
│
DevFreela.Core
│
├── Entities
├── Repositories
├── Services
├── Models
│
DevFreela.Infrastructure
│
├── Persistence
├── Repositories
├── Services
│
DevFreela.UnitTests
```

### Request Flow

```text
HTTP Request
      ↓
Controller
      ↓
MediatR
      ↓
Command / Query
      ↓
Handler
      ↓
Repository
      ↓
Database
```

## Main Endpoints

### Authentication

```http
PUT /api/users/login
```

### Users

```http
GET    /api/users
GET    /api/users/{id}
POST   /api/users
```

### Projects

```http
GET    /api/projects
GET    /api/projects/{id}
POST   /api/projects
PUT    /api/projects/{id}
DELETE /api/projects/{id}
PUT    /api/projects/{id}/start
PUT    /api/projects/{id}/complete
POST   /api/projects/{id}/comments
```

## Getting Started

### Prerequisites

* .NET 8 SDK
* SQL Server
* Visual Studio 2022 or JetBrains Rider

### Clone the Repository

```bash
git clone https://github.com/ocainadev/freelancer-management-api.git
cd freelancer-management-api
```

### Configure the Database

Update the connection string in:

```text
appsettings.json
```

### Apply Migrations

```bash
dotnet ef database update
```

### Run the Application

```bash
dotnet run --project DevFreela.API
```

## Testing

Run all tests:

```bash
dotnet test
```

## Concepts Demonstrated

* Clean Architecture
* CQRS Pattern
* MediatR
* Dependency Injection
* Repository Pattern
* Entity Framework Core
* JWT Authentication
* Authorization Policies
* Domain Modeling
* Unit Testing
* RESTful API Design

## Future Improvements

* Refresh Tokens
* Docker Support
* Integration Tests
* API Versioning
* Background Jobs
* Redis Caching
* File Upload Integration
* Swagger Authentication Support

## Author

Cainã Santos

GitHub: https://github.com/ocainadev

## License

This project is available for educational and portfolio purposes.
