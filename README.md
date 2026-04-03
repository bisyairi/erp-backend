# ERP System — Backend (Spring Boot)

> Enterprise Resource Planning system built with Spring Boot + MySQL. Part of a 2-project portfolio showcasing multi-stack development.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | Spring Boot 3.x |
| Language | Java 17 |
| Database | MySQL 8.x |
| Auth | JWT + Spring Security |
| ORM | JPA / Hibernate |
| Build Tool | Maven |
| API Style | REST API (JSON) |

---

## Features

- JWT Authentication with role-based access (Admin / Manager / Staff)
- Inventory Management — products, stock tracking, low stock alerts
- Purchase Order — create, approve/reject workflow
- Supplier Management
- HR / Employee records
- Dashboard summary & charts
- REST API for Vendor Portal integration

---

## Prerequisites

Make sure you have these installed:

- Java 17+
- Maven 3.8+
- MySQL 8.x
- Git

---

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/bisyairi/erp-backend.git
cd erp-backend
```

### 2. Setup database

```sql
CREATE DATABASE erp_db;
CREATE USER 'erp_user'@'localhost' IDENTIFIED BY 'yourpassword';
GRANT ALL PRIVILEGES ON erp_db.* TO 'erp_user'@'localhost';
FLUSH PRIVILEGES;
```

### 3. Configure environment

Copy the example config:

```bash
cp src/main/resources/application-dev.yml.example src/main/resources/application-dev.yml
```

Edit `application-dev.yml`:

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/erp_db
    username: erp_user
    password: yourpassword

jwt:
  secret: your-secret-key-here-min-32-chars
  expiration: 86400000  # 24 hours in ms
```

### 4. Run the app

```bash
mvn spring-boot:run -Dspring-boot.run.profiles=dev
```

App will start at `http://localhost:8080`

---

## API Base URL

```
http://localhost:8080/api/v1
```

Full API documentation: see `erp_api_docs.docx` or Postman collection in `/docs` folder.

---

## Default Admin Account

After first run, a default admin account is seeded:

```
Email:    admin@erp.com
Password: Admin@1234
```

> **Change this immediately in production!**

---

## Project Structure

```
src/main/java/dev/bisyairi/erp/
├── config/          # Security, JWT config
├── controller/      # REST controllers
├── service/         # Business logic
├── repository/      # JPA repositories
├── model/           # Entity classes
├── dto/             # Request/Response DTOs
├── exception/       # Custom exceptions
└── util/            # Helper utilities
```

---

## Running Tests

```bash
mvn test
```

---

## Docker (Optional)

```bash
docker-compose up -d
```

Requires `docker-compose.yml` in root directory.

---

## Related Projects

| Project | Repo | Description |
|---|---|---|
| ERP Frontend | [erp-frontend](https://github.com/bisyairi/erp-frontend) | React + shadcn/ui |
| Vendor Portal | [vendor-portal](https://github.com/bisyairi/vendor-portal) | Laravel + Nuxt 3 |

---

## Author

**Bisyairi Bin Mohamad Hasbi**
- Website: [bisyairi.dev](https://bisyairi.dev)
- GitHub: [@bisyairi](https://github.com/bisyairi)

---

## License

MIT License — feel free to use for learning purposes.