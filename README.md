# Spring Boot RESTful API with MySQL and Validation

This project is a RESTful API for managing books, built with Spring Boot, connected to a MySQL database, and includes input validation using Jakarta Validation.

---

## Project Setup

### Prerequisites

- Java 24 or higher
- Maven 3.6 or higher
- MySQL server running on port 3306
- An IDE such as IntelliJ IDEA, VSCode, or Eclipse

### Database Setup

1. Open your MySQL client and create the database:

```sql
CREATE DATABASE Library;
```
2. Configure the database connection in src/main/resources/application.properties:

```
spring.datasource.url=jdbc:mysql://localhost:3306/books_db?useSSL=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
```
## Running the Application

To run the application:

Open a terminal in the project root folder.
Run:
```
mvn clean spring-boot:run
```
The API will start and listen on: http://localhost:8080

## API Endpoints and Sample Requests

1. Get all books
   Method: GET
   URL: /api/books
```
http://localhost:8080/api/books
```
2. Get a book by ID
   Method: GET
   URL: /api/books/{id}
```
http://localhost:8080/api/books/1
```
3. Create a new book
   Method: POST
   URL: /api/books
   Headers: Content-Type: application/json
   Body example:
```
   {
   "title": "Test",
   "author": "Test",
   "isbn": "Testfds2",
   "publishedDate": "2001-04-01",
   "genre": "Test",
   "price": 50.50
   }
```