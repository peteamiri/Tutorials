# Java Design Patterns

## Resources

* [GitHub Resource](https://github.com/iluwatar/java-design-patterns)

Absolutely! Here's a **detailed and logically structured table of contents** for a **technical book on Java Design Patterns**. This outline covers all the **Gang of Four (GoF)** design patterns and goes further to include **modern patterns**, **best practices**, and **real-world Java applications**, making it suitable for intermediate to advanced Java developers.

---

# 📘 **Table of Contents – *Mastering Java Design Patterns***  

---

## **Preface**
- Why Design Patterns Matter  
- How to Use This Book  
- Audience and Prerequisites  
- Tools and Setup (JDK, IDEs, UML Tools)  
- Conventions Used in Code Examples  

---

## **Part I: Introduction to Design Patterns**

### 1. **Understanding Design Patterns**
- What Are Design Patterns?  
- History and Origins (Gang of Four)  
- Principles Behind Patterns (DRY, SOLID, KISS, etc.)  
- Categories of Patterns  
- Benefits and Limitations  
- Pattern Syntax and UML Basics  

### 2. **Java Language Features Supporting Patterns**
- OOP in Java: Inheritance, Interfaces, Polymorphism  
- Java 8+ Features: Lambdas, Streams, Optional  
- Enums, Generics, Reflection, and Annotations  
- Dependency Injection and Composition Over Inheritance  

---

## **Part II: Creational Design Patterns**

### 3. **Singleton Pattern**
- Lazy vs Eager Initialization  
- Thread Safety and Double-Checked Locking  
- Enum-based Singleton  
- Use Cases and Pitfalls  

### 4. **Factory Method Pattern**
- Static Factory Methods  
- Abstract Factory vs Factory Method  
- Real-World Scenarios (e.g., UI Toolkit, Logging)  

### 5. **Abstract Factory Pattern**
- Providing Families of Related Objects  
- Implementing with Interfaces and Factories  
- Extending to New Product Families  

### 6. **Builder Pattern**
- Handling Complex Object Creation  
- Fluent Interfaces and Method Chaining  
- Director and Concrete Builders  

### 7. **Prototype Pattern**
- Cloning Objects in Java  
- Shallow vs Deep Copy  
- Cloning via Serialization  

---

## **Part III: Structural Design Patterns**

### 8. **Adapter Pattern**
- Class vs Object Adapters  
- Real-World Use Cases (Legacy Code Integration, Java I/O)  
- Wrapping APIs in Modern Interfaces  

### 9. **Bridge Pattern**
- Decoupling Abstraction from Implementation  
- Interface Layering  
- Useful in UI Frameworks and Communication Layers  

### 10. **Composite Pattern**
- Treating Individual and Composite Objects Uniformly  
- Tree Structures (e.g., File Systems, Menus)  
- Implementation Using Recursion  

### 11. **Decorator Pattern**
- Adding Behavior Dynamically  
- Comparison with Inheritance  
- Real-World Java Examples (Streams, Filters)  

### 12. **Facade Pattern**
- Simplifying Complex Subsystems  
- Designing Clean API Interfaces  
- Practical Applications in Libraries  

### 13. **Flyweight Pattern**
- Memory Optimization Through Shared Objects  
- Intrinsic vs Extrinsic State  
- Use in Game Development and GUIs  

### 14. **Proxy Pattern**
- Virtual, Remote, and Protection Proxies  
- Implementing with Interfaces  
- Examples: Lazy Loading, Security, Logging  

---

## **Part IV: Behavioral Design Patterns**

### 15. **Chain of Responsibility Pattern**
- Passing Requests Along a Chain  
- Event Processing Pipelines  
- Logging and Middleware Frameworks  

### 16. **Command Pattern**
- Encapsulating Actions as Objects  
- Queuing, Undo/Redo  
- GUI Buttons and Macros  

### 17. **Interpreter Pattern**
- Designing Simple Languages or Expression Parsers  
- Grammar Rules as Classes  
- Calculator and Rule Engine Examples  

### 18. **Iterator Pattern**
- Sequential Access Without Exposing Structure  
- Custom Collections and Iterators  
- Java's `Iterator` and `Iterable` Interfaces  

### 19. **Mediator Pattern**
- Reducing Object Interdependency  
- Centralized Control for UI Elements or Components  
- Chat Room and Event Bus Examples  

### 20. **Memento Pattern**
- Capturing and Restoring Object State  
- Implementing Undo Functionality  
- Deep Copy Techniques  

### 21. **Observer Pattern**
- One-to-Many Event Notification  
- `java.util.Observer` and `PropertyChangeListener`  
- Event Listeners, Pub-Sub Systems  

### 22. **State Pattern**
- Changing Behavior Based on Internal State  
- Replacing Conditionals with Polymorphism  
- Finite State Machines  

### 23. **Strategy Pattern**
- Selecting Algorithms at Runtime  
- Encapsulating Algorithms  
- Java Comparators, Encryption Algorithms  

### 24. **Template Method Pattern**
- Defining Skeleton of an Algorithm  
- Reuse and Extension of Core Logic  
- Hook Methods and Default Behaviors  

### 25. **Visitor Pattern**
- Adding Behavior Without Modifying Classes  
- Traversing Object Structures  
- Java Compilers and Tree Walkers  

---

## **Part V: Architectural & Modern Patterns**

### 26. **Model-View-Controller (MVC)**
- Separating Concerns  
- Implementation in Java SE and JavaFX  
- MVC vs MVP vs MVVM  

### 27. **Dependency Injection Pattern**
- Loose Coupling with Inversion of Control  
- Manual DI, Java Service Loader, and Spring Overview  

### 28. **Builder vs Factory vs Prototype: When to Use What**
- Comparing Similar Creational Patterns  
- Choosing Based on Use Case and Complexity  

### 29. **Reactive and Event-Driven Patterns**
- Observer vs Event Bus vs Publisher-Subscriber  
- Reactive Streams and Functional Event Systems  
- Applying Patterns with Java’s `Flow` API and RxJava  

### 30. **Null Object and Object Pool Patterns**
- Avoiding Nulls with Null Object  
- Reusing Objects with Object Pools  
- Implementation in Game Engines and Resource Management  

---

## **Part VI: Practical Applications and Case Studies**

### 31. **Design Patterns in Real-World Java Frameworks**
- Spring Framework: Singleton, Proxy, FactoryBean  
- Java Collections: Iterator, Composite, Strategy  
- Java I/O/NIO: Decorator, Adapter  

### 32. **Design Patterns in Java GUI Development**
- Swing, JavaFX, Android Patterns  
- MVC, Observer, Command in UI Components  

### 33. **Refactoring to Patterns**
- Identifying Code Smells  
- Applying Design Patterns for Clean Code  
- Before/After Examples  

### 34. **Testing Design Pattern Implementations**
- Unit Testing Pattern Implementations  
- Mocking, Dependency Injection, and Patterns  
- Patterns for Testable Code  

---

## **Appendices**

- A. Design Pattern Reference Cards  
- B. UML Diagrams of All Patterns  
- C. Common Anti-Patterns and How to Avoid Them  
- D. Interview Questions on Design Patterns  
- E. Further Reading and Resources (Books, Articles, Tools)  
- F. Pattern Naming Cheat Sheet  

---

Would you like this as a structured **course curriculum**, or maybe broken into **chapter-length summaries with example projects**? I can also tailor this for a specific audience (e.g., junior devs, architects, or job interview prep).
