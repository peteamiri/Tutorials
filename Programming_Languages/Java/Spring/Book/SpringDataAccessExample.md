### **Example: Data Access in Spring with Spring Data JPA**

In this example, we will build a Spring Boot application that demonstrates how to access and manage data in a database using **Spring Data JPA**. We’ll create a simple **Bookstore Application** where we manage books, their authors, and their prices. This will showcase the data access layer, using JPA (Java Persistence API) and Spring Data JPA for interacting with the database.

### **Project Overview**

We will use the following technologies:
- **Spring Boot** for setting up the project and application context.
- **Spring Data JPA** for simplifying database operations.
- **H2 Database** as an in-memory database for quick testing and development.
- **Lombok** to reduce boilerplate code for entity classes.

---

### **Step 1: Set Up the Project**

First, generate a Spring Boot project using **Spring Initializr** (or manually by adding the dependencies to your `pom.xml`). The following dependencies are necessary for this project:
- **Spring Web** for creating RESTful APIs.
- **Spring Data JPA** for easy database access and management.
- **H2 Database** for a lightweight, in-memory database for testing.
- **Lombok** to reduce boilerplate code (getters, setters, constructors).

Here’s the `pom.xml` content for Maven:

```xml
<dependencies>
    <!-- Spring Boot Web Dependency -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>

    <!-- Spring Boot Data JPA Dependency -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>

    <!-- H2 In-Memory Database -->
    <dependency>
        <groupId>com.h2database</groupId>
        <artifactId>h2</artifactId>
        <scope>runtime</scope>
    </dependency>

    <!-- Lombok for reducing boilerplate code -->
    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <scope>provided</scope>
    </dependency>

    <!-- Spring Boot DevTools for development -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-devtools</artifactId>
        <scope>runtime</scope>
    </dependency>

    <!-- Spring Boot Testing Dependencies -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>
```

---

### **Step 2: Configure the Database in `application.properties`**

Now, configure the database connection in the `application.properties` file:

```properties
# H2 Database configuration (in-memory)
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect

# Hibernate DDL auto generation strategy
spring.jpa.hibernate.ddl-auto=update

# Show SQL queries in console for debugging
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
```

- **`spring.datasource.url`**: This URL connects to an H2 in-memory database (`mem:testdb` means the database is in memory and will be deleted once the application stops).
- **`spring.jpa.hibernate.ddl-auto=update`**: Automatically updates the database schema based on the entity classes.

---

### **Step 3: Define the `Book` Entity**

Next, we create the **Book** entity class that will be mapped to the database table.

```java
package com.example.bookstore.model;

import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.NoArgsConstructor;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
@Data
@NoArgsConstructor
@AllArgsConstructor
public class Book {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String title;
    private String author;
    private Double price;
}
```

- **`@Entity`**: Marks the class as a JPA entity, which will be mapped to a database table.
- **`@Id`**: Denotes the primary key of the entity.
- **`@GeneratedValue(strategy = GenerationType.IDENTITY)`**: Specifies that the primary key should be auto-generated.

- **`@Data`**: Lombok annotation that automatically generates getters, setters, `toString()`, `equals()`, and `hashCode()` methods.
- **`@NoArgsConstructor`** and **`@AllArgsConstructor`**: Lombok annotations to generate a no-argument constructor and a constructor with all arguments.

---

### **Step 4: Create the `BookRepository` Interface**

The `BookRepository` interface extends `JpaRepository`, which is a Spring Data interface that provides CRUD operations for the `Book` entity.

```java
package com.example.bookstore.repository;

import com.example.bookstore.model.Book;
import org.springframework.data.jpa.repository.JpaRepository;

public interface BookRepository extends JpaRepository<Book, Long> {
    // You can define custom queries here if needed
}
```

- **`JpaRepository<Book, Long>`**: By extending `JpaRepository`, we get access to all CRUD methods like `findAll()`, `findById()`, `save()`, `delete()`, etc. The generic parameters specify that we are working with the `Book` entity and the primary key type is `Long`.

---

### **Step 5: Create the `BookService` Layer**

The service layer handles business logic. It interacts with the repository and performs CRUD operations.

```java
package com.example.bookstore.service;

import com.example.bookstore.model.Book;
import com.example.bookstore.repository.BookRepository;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import java.util.List;
import java.util.Optional;

@Service
public class BookService {

    @Autowired
    private BookRepository bookRepository;

    // Get all books
    public List<Book> getAllBooks() {
        return bookRepository.findAll();
    }

    // Get a book by its ID
    public Optional<Book> getBookById(Long id) {
        return bookRepository.findById(id);
    }

    // Add a new book
    public Book addBook(Book book) {
        return bookRepository.save(book);
    }

    // Update an existing book
    public Book updateBook(Long id, Book bookDetails) {
        Optional<Book> book = bookRepository.findById(id);
        if (book.isPresent()) {
            Book updatedBook = book.get();
            updatedBook.setTitle(bookDetails.getTitle());
            updatedBook.setAuthor(bookDetails.getAuthor());
            updatedBook.setPrice(bookDetails.getPrice());
            return bookRepository.save(updatedBook);
        }
        return null; // Return null or throw an exception
    }

    // Delete a book by its ID
    public void deleteBook(Long id) {
        bookRepository.deleteById(id);
    }
}
```

- **`@Service`**: This annotation marks the class as a service, which means it will be used for business logic and injected into other components like controllers.
- **`@Autowired`**: Automatically injects the `BookRepository` dependency into the service.

---

### **Step 6: Create the `BookController` (RESTful API Layer)**

The controller layer defines the RESTful endpoints that the client can call to interact with the application.

```java
package com.example.bookstore.controller;

import com.example.bookstore.model.Book;
import com.example.bookstore.service.BookService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.*;

import java.util.List;
import java.util.Optional;

@RestController
@RequestMapping("/api/books")
public class BookController {

    @Autowired
    private BookService bookService;

    // Get all books
    @GetMapping
    public List<Book> getAllBooks() {
        return bookService.getAllBooks();
    }

    // Get a book by ID
    @GetMapping("/{id}")
    public Optional<Book> getBookById(@PathVariable Long id) {
        return bookService.getBookById(id);
    }

    // Create a new book
    @PostMapping
    public Book addBook(@RequestBody Book book) {
        return bookService.addBook(book);
    }

    // Update an existing book
    @PutMapping("/{id}")
    public Book updateBook(@PathVariable Long id, @RequestBody Book book) {
        return bookService.updateBook(id, book);
    }

    // Delete a book by ID
    @DeleteMapping("/{id}")
    public void deleteBook(@PathVariable Long id) {
        bookService.deleteBook(id);
    }
}
```

- **`@RestController`**: A specialized version of `@Controller`, used to expose REST endpoints. The methods in this class will return JSON data instead of views.
- **`@RequestMapping("/api/books")`**: Base URL path for the controller's endpoints.
- **`@GetMapping`, `@PostMapping`, `@PutMapping`, `@DeleteMapping`**: These annotations map HTTP requests (GET, POST, PUT, DELETE) to specific methods.

---

### **Step 7: Running the Application**

The main entry point for the Spring Boot application is the `BookstoreApplication` class. This class will launch the application.

```java
package com.example.bookstore;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class BookstoreApplication {

    public static void main(String[] args) {
        SpringApplication.run(BookstoreApplication.class, args);
    }
}
```

- **`@SpringBootApplication`**: Marks the main class of the Spring Boot application. It enables component scanning, auto-configuration, and property support.

---

### **Step 8: Testing the Application**

After running the application, you can test the API using tools like **Postman** or **curl**.

Here are the endpoints you can test:

- **GET** `/api/books`: Get all books.
- **GET** `/api/books/{id}`: Get a book by ID.
- **POST** `/api/books`: Create a new book (send JSON in the request body).
- **PUT** `/api/books/{id}`: Update an existing book.
- **DELETE** `/api/books/{id}`: Delete a book by ID.

---

### **Conclusion**

In this example, we demonstrated how to implement data access in Spring using **Spring Data JPA**. The application uses:
- **Spring Data JPA** for database interactions, providing simple CRUD operations via the `JpaRepository`.
- **Spring Boot** for setting up and running the application quickly.
- **A RESTful API** exposed via a Spring controller to handle book-related operations.

This architecture follows the **separation of concerns** pattern by dividing the project into entities, repositories, services, and controllers, which is a common best practice in Spring applications.
