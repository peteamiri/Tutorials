### **Example Spring Boot Project: A RESTful API for a Bookstore**

In this example, we'll create a simple Spring Boot application that exposes a RESTful API for managing books in a bookstore. This project will include features such as creating, reading, updating, and deleting books (CRUD operations), and will be integrated with a database using Spring Data JPA.

### **Step-by-Step Walkthrough of the Project**

---

### **1. Project Setup**

We'll start by generating a Spring Boot project using **Spring Initializr** or manually setting up dependencies in your IDE.

#### **Dependencies to Add:**
- **Spring Web**: For creating RESTful services.
- **Spring Data JPA**: For interacting with the database using JPA (Java Persistence API).
- **H2 Database**: In-memory database for testing purposes.
- **Spring Boot DevTools**: Provides automatic restarts for development.
- **Lombok**: Reduces boilerplate code (like getters, setters, constructors, etc.).
- **Spring Boot Starter Test**: For writing and running tests.

You can generate the project from [Spring Initializr](https://start.spring.io/) with the necessary dependencies or add them manually in your `pom.xml` file if you are using Maven.

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>
    <dependency>
        <groupId>com.h2database</groupId>
        <artifactId>h2</artifactId>
        <scope>runtime</scope>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-devtools</artifactId>
        <scope>runtime</scope>
    </dependency>
    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <scope>provided</scope>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>
```

---

### **2. Project Structure**

Here is a typical project structure for this example:

```
src/
 └── main/
     └── java/
         └── com/
             └── example/
                 └── bookstore/
                     ├── BookstoreApplication.java
                     ├── controller/
                     │   └── BookController.java
                     ├── model/
                     │   └── Book.java
                     ├── repository/
                     │   └── BookRepository.java
                     └── service/
                         └── BookService.java
     └── resources/
         ├── application.properties
```

### **3. Defining the Book Entity**

The `Book` class represents the entity (model) that will be mapped to the database.

```java
package com.example.bookstore.model;

import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.NoArgsConstructor;

import javax.persistence.Entity;
import javax.persistence.Id;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;

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

- **@Entity**: Marks this class as a JPA entity that will be mapped to a database table.
- **@Id**: Marks the primary key.
- **@GeneratedValue**: Specifies the strategy for generating the ID (e.g., auto-increment).

### **4. Creating the Repository Layer**

The repository interface provides an abstraction for accessing the database. It extends `JpaRepository`, providing built-in methods for CRUD operations.

```java
package com.example.bookstore.repository;

import com.example.bookstore.model.Book;
import org.springframework.data.jpa.repository.JpaRepository;

public interface BookRepository extends JpaRepository<Book, Long> {
    // Custom query methods can be added here if necessary
}
```

- **JpaRepository**: A Spring Data JPA interface that provides methods like `findAll()`, `findById()`, `save()`, and `delete()` out of the box.

### **5. Creating the Service Layer**

The service layer handles the business logic. Here, we'll define a simple service that interacts with the repository to perform CRUD operations.

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

    public List<Book> getAllBooks() {
        return bookRepository.findAll();
    }

    public Optional<Book> getBookById(Long id) {
        return bookRepository.findById(id);
    }

    public Book addBook(Book book) {
        return bookRepository.save(book);
    }

    public Book updateBook(Long id, Book bookDetails) {
        Optional<Book> existingBook = bookRepository.findById(id);
        if (existingBook.isPresent()) {
            Book updatedBook = existingBook.get();
            updatedBook.setTitle(bookDetails.getTitle());
            updatedBook.setAuthor(bookDetails.getAuthor());
            updatedBook.setPrice(bookDetails.getPrice());
            return bookRepository.save(updatedBook);
        }
        return null;  // You could throw an exception here for better error handling
    }

    public void deleteBook(Long id) {
        bookRepository.deleteById(id);
    }
}
```

- **@Service**: Marks the class as a service, making it a Spring bean that can be injected into other components (like the controller).
- **@Autowired**: Injects the `BookRepository` into the service class.

### **6. Creating the Controller Layer**

The controller layer will define the REST endpoints for interacting with the `BookService` and handling HTTP requests.

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

    // Get a book by id
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

    // Delete a book by id
    @DeleteMapping("/{id}")
    public void deleteBook(@PathVariable Long id) {
        bookService.deleteBook(id);
    }
}
```

- **@RestController**: A convenience annotation that combines `@Controller` and `@ResponseBody`, making it ideal for RESTful APIs.
- **@RequestMapping("/api/books")**: Defines the base URL path for this controller.
- **@GetMapping, @PostMapping, @PutMapping, @DeleteMapping**: Map HTTP methods to Java methods.

### **7. Configuring the Application**

In the `application.properties` file, you configure the database connection and other settings.

```properties
# DataSource Configuration (H2 Database)
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect

# Hibernate Configuration
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

- **spring.datasource.url**: Configures the H2 database in memory.
- **spring.jpa.hibernate.ddl-auto=update**: Automatically creates or updates database schema based on the JPA entity classes.

### **8. Running the Application**

In the `BookstoreApplication.java` class, add the `@SpringBootApplication` annotation and run the application:

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

---

### **9. Testing the API**

Once the application is up and running, you can test the API using tools like Postman or `curl`.

#### Example API calls:

- **GET** `/api/books` – Get all books.
- **GET** `/api/books/{id}` – Get a book by its ID.
- **POST** `/api/books` – Create a new book (provide JSON in the body).
- **PUT** `/api/books/{id}` – Update an existing book.
- **DELETE** `/api/books/{id}` – Delete a book by ID.

---

### **10. Conclusion**

This Spring Boot application demonstrates how to quickly build a RESTful API with CRUD operations using Spring Data JPA. It uses a simple in-memory H2 database, but you can easily switch to a persistent database like MySQL or PostgreSQL by updating the `application.properties` file.

This example can be extended by adding more features such as validation, exception handling, pagination, and custom queries.
