### **Example: Web Development with Spring Boot**

In this example, we will create a **Web Application** using **Spring Boot** that serves dynamic content using **Thymeleaf** templates. This application will allow users to manage books in a bookstore, where they can view a list of books, add new books, and edit existing ones. We will also integrate **Spring Data JPA** for database operations and use **Spring MVC** for the web layer.

### **Project Overview**

We'll create the following features in this web application:
1. View a list of books.
2. Add a new book to the list.
3. Edit an existing book.
4. Use **Thymeleaf** for rendering HTML templates.
5. Use **Spring Data JPA** for managing data persistence.

---

### **Step 1: Project Setup**

Generate a new Spring Boot project using **Spring Initializr** or your IDE’s Spring Boot project generator with the following dependencies:
- **Spring Web**: For building the web layer with Spring MVC.
- **Spring Data JPA**: For interacting with the database.
- **Thymeleaf**: For rendering dynamic HTML pages.
- **H2 Database**: In-memory database for quick development and testing.
- **Lombok**: For reducing boilerplate code (getters, setters, constructors).

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

    <!-- Thymeleaf Template Engine Dependency -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-thymeleaf</artifactId>
    </dependency>

    <!-- H2 In-Memory Database for Development and Testing -->
    <dependency>
        <groupId>com.h2database</groupId>
        <artifactId>h2</artifactId>
        <scope>runtime</scope>
    </dependency>

    <!-- Lombok Dependency for Reducing Boilerplate Code -->
    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <scope>provided</scope>
    </dependency>

    <!-- Spring Boot Test Dependency for Testing -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>
```

---

### **Step 2: Configure Database Connection**

In the `application.properties` file, configure the H2 database connection and other necessary settings.

```properties
# H2 In-Memory Database Configuration
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect

# Hibernate DDL Auto-Update Configuration
spring.jpa.hibernate.ddl-auto=update

# Show SQL Queries in the Console
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

# Thymeleaf Configuration
spring.thymeleaf.prefix=classpath:/templates/
spring.thymeleaf.suffix=.html
```

- **`spring.datasource.url`**: Specifies the in-memory database connection URL.
- **`spring.jpa.hibernate.ddl-auto=update`**: Automatically updates the database schema on startup.
- **`spring.thymeleaf.prefix`** and **`spring.thymeleaf.suffix`**: Configures the location of the Thymeleaf templates.

---

### **Step 3: Define the `Book` Entity**

The `Book` class represents a book in the bookstore. It will be mapped to a table in the database using JPA annotations.

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

- **`@Entity`**: Marks this class as a JPA entity, which will be mapped to a database table.
- **`@Id`** and **`@GeneratedValue(strategy = GenerationType.IDENTITY)`**: Specifies that `id` is the primary key, and its value is auto-generated.

---

### **Step 4: Create the `BookRepository` Interface**

The `BookRepository` interface extends `JpaRepository`, providing built-in methods for CRUD operations on the `Book` entity.

```java
package com.example.bookstore.repository;

import com.example.bookstore.model.Book;
import org.springframework.data.jpa.repository.JpaRepository;

public interface BookRepository extends JpaRepository<Book, Long> {
}
```

- **`JpaRepository<Book, Long>`**: Extending `JpaRepository` provides methods like `findAll()`, `findById()`, `save()`, and `deleteById()` for interacting with the `Book` entity.

---

### **Step 5: Create the `BookService` Layer**

The `BookService` class contains the business logic and interacts with the repository to perform CRUD operations.

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

    // Get a book by ID
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
        return null; // Return null or throw an exception if not found
    }

    // Delete a book by ID
    public void deleteBook(Long id) {
        bookRepository.deleteById(id);
    }
}
```

- **`@Service`**: Marks the class as a service to handle business logic.
- **`@Autowired`**: Injects the `BookRepository` into the service.

---

### **Step 6: Create the `BookController` (Web Layer)**

The `BookController` class is responsible for handling HTTP requests and rendering views using Thymeleaf.

```java
package com.example.bookstore.controller;

import com.example.bookstore.model.Book;
import com.example.bookstore.service.BookService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.*;

@Controller
@RequestMapping("/books")
public class BookController {

    @Autowired
    private BookService bookService;

    // Display list of books
    @GetMapping
    public String getAllBooks(Model model) {
        model.addAttribute("books", bookService.getAllBooks());
        return "book-list"; // Return the view name to be rendered by Thymeleaf
    }

    // Show form to add a new book
    @GetMapping("/add")
    public String showAddForm(Model model) {
        model.addAttribute("book", new Book());
        return "book-form"; // Return the form view
    }

    // Handle form submission to add a new book
    @PostMapping("/add")
    public String addBook(@ModelAttribute Book book) {
        bookService.addBook(book);
        return "redirect:/books"; // Redirect to the list of books
    }

    // Show form to edit an existing book
    @GetMapping("/edit/{id}")
    public String showEditForm(@PathVariable("id") Long id, Model model) {
        model.addAttribute("book", bookService.getBookById(id).orElse(null));
        return "book-form"; // Return the form view for editing
    }

    // Handle form submission to update an existing book
    @PostMapping("/edit/{id}")
    public String updateBook(@PathVariable("id") Long id, @ModelAttribute Book book) {
        bookService.updateBook(id, book);
        return "redirect:/books"; // Redirect to the list of books
    }

    // Handle book deletion
    @GetMapping("/delete/{id}")
    public String deleteBook(@PathVariable("id") Long id) {
        bookService.deleteBook(id);
        return "redirect:/books"; // Redirect to the list of books after deletion
    }
}
```

- **`@Controller`**: Marks the class as a Spring MVC controller that handles web requests and renders views.
- **`@RequestMapping("/books")`**: Specifies the base URL for the controller.
- **`@GetMapping`, `@PostMapping`**: These annotations map HTTP GET and POST requests to specific methods.

The `Model` object is used to pass data from the controller to the Thymeleaf views.

---

### **Step 7: Create the Thymeleaf Templates**

1. **Book List Template (`book-list.html`)**:

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Bookstore</title>
</head>
<body>
    <h1>Book List</h1>
    <table>
        <tr>
            <th>Title</th>
            <th>Author</th>
            <th>Price</th>
            <th>Actions</th>
        </tr>
        <tr th:each="book : ${books}">
            <td th:text="${book.title}"></td>
            <td th:text="${book.author}"></td>
            <td th:text="${book.price}"></td>
            <td>
                <a th:href="@{/books/edit/{id}(id=${book.id})}">Edit</a> |
                <a th:href="@{/books/delete/{id}(id=${book.id})}">Delete</a>
            </td>
        </tr>
    </table>
    <a href="/books/add">Add New Book</a>
</body>
</html>
```

2. **Book Form Template (`book-form.html`)**:

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Book Form</title>
</head>
<body>
    <h1 th:text="${book.id == null ? 'Add a New Book' : 'Edit Book'}"></h1>
    <form th:action="@{/books/add}" th:object="${book}" method="post">
        <label for="title">Title:</label>
        <input type="text" th:field="*{title}" /><br>
        <label for="author">Author:</label>
        <input type="text" th:field="*{author}" /><br>
        <label for="price">Price:</label>
        <input type="text" th:field="*{price}" /><br>
        <button type="submit">Submit</button>
    </form>
    <a href="/books">Back to List</a>
</body>
</html>
```

- **`th:each`**: Loops through a list of books and generates rows for each book.
- **`th:field`**: Binds form fields to the `Book` object passed from the controller.
- **`th:href`**: Generates dynamic URLs for edit and delete actions.

---

### **Step 8:

 Running the Application**

Finally, run the application using your IDE or by executing:

```bash
mvn spring-boot:run
```

After the application starts, navigate to:

- **`http://localhost:8080/books`**: Displays the list of books.
- **`http://localhost:8080/books/add`**: Opens the form to add a new book.
- **`http://localhost:8080/books/edit/{id}`**: Opens the form to edit an existing book.

---

### **Conclusion**

In this example, we demonstrated how to create a web application with **Spring Boot** and **Spring MVC**. The application allows users to:
- View a list of books.
- Add new books.
- Edit and delete books.

We used **Thymeleaf** to render dynamic HTML pages and **Spring Data JPA** for database operations. This example is a typical architecture for web applications with Spring, adhering to the separation of concerns between the controller, service, and repository layers.
