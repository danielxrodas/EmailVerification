# 📧 Email Verification Backend

This is a Spring Boot backend project that provides a secure user **signup and login system** using **email verification** and **JWT authentication**.  
No frontend/UI is included — this is designed as a backend API that can be consumed by any frontend application or mobile client.

---

## 🔐 Features

- Secure user signup with email verification
- JWT token generation for authenticated access
- Resend verification code support
- Stateless Spring Security configuration with filters
- Environment-based configuration using `.env` variables or `application.properties`

---

## 🛠 Tech Stack

- Java 17+
- Spring Boot
- Spring Security
- JWT (JSON Web Tokens)
- PostgreSQL (or pluggable DB)
- JavaMailSender (SMTP/Gmail)
- Maven or Gradle

---

## 📬 API Endpoints

| Endpoint        | Method | Description                               |
|-----------------|--------|-------------------------------------------|
| `/auth/signup`  | POST   | Register a new user (sends email code)     |
| `/auth/verify`  | POST   | Verifies the user via code                 |
| `/auth/resend`  | POST   | Resends the verification code              |
| `/auth/login`   | POST   | Logs in verified users, returns JWT token  |

---

## 📄 Sample Signup Flow

1. User signs up at `/auth/signup`
2. A verification code is sent to the user’s email
3. User submits the code to `/auth/verify`
4. If verified, the user can log in at `/auth/login` and receive a JWT token

---

## 🧪 Testing

You can test this API using tools like:

- [Postman](https://www.postman.com/)
- Any HTTP client of your choice

---

## ⚙️ Environment Configuration

Set up your SMTP and database credentials in `application.properties` or use a `.env` loader:

```properties
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your_email@gmail.com
spring.mail.password=your_app_password
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true

spring.datasource.url=jdbc:postgresql://localhost:5432/your_db
spring.datasource.username=your_db_user
spring.datasource.password=your_db_password
