# Forum Hub

REST API built with Spring Boot for a discussion forum. Supports full
CRUD on topics and uses JWT-based authentication to secure every request.

![Java](https://img.shields.io/badge/Java_17-ED8B00?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat&logo=springsecurity&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Flyway](https://img.shields.io/badge/Flyway-CC0200?style=flat&logo=flyway&logoColor=white)

## Endpoints

### Authentication

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/auth` | Login and get JWT token |

Request body:
```json
{
  "login": "usuario",
  "clave": "password"
}
```

### Topics

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/topicos` | List all topics |
| POST | `/topicos` | Create a new topic |
| PUT | `/topicos` | Update an existing topic |
| DELETE | `/topicos/{id}` | Delete a topic by ID |

POST / PUT body:
```json
{
  "titulo": "Topic title",
  "mensaje": "Topic message",
  "nombreCurso": "Course name"
}
```

> All endpoints except `/auth` require the header `Authorization: Bearer `

## Getting started

### Prerequisites

- Java 17+
- MySQL running locally
- Maven

### Installation

```bash
# 1. Clone the repository
https://github.com/Ccirhack/forum-hub-java
cd forum-hub-java

# 2. Configure your database in src/main/resources/application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/forohub
spring.datasource.username=YOUR_USER
spring.datasource.password=YOUR_PASSWORD
api.security.secret=YOUR_JWT_SECRET

# 3. Build and run (Flyway will create the tables automatically)
mvn clean install
mvn spring-boot:run
```

## Tech stack

- Java 17, Spring Boot, Spring Security, Spring Data JPA
- Flyway for database migrations
- Lombok for boilerplate reduction
- MySQL as database
- Maven as build tool

## What I learned

- Securing a REST API with JWT and Spring Security
- Database versioning with Flyway migrations
- Input validation with Bean Validation
- Clean layered architecture with DTOs and repositories

## Contributing

Contributions are welcome. Open an issue first to discuss changes,
then submit a pull request.

## Contact

Yuan Retamozo · [LinkedIn](https://www.linkedin.com/in/yuan-retamozo/) · yretamozovilca@gmail.com
