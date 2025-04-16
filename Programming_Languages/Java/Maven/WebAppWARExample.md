Sure! Below is a **detailed example** of using **Maven** for a **Java web application** with **WAR (Web ARchive) packaging**. This application will use **Servlets** and **JSP** for handling requests, and it will be packaged as a WAR file for deployment to a **Servlet container** like **Tomcat** or **Jetty**.

---

# 🌐 Maven Web Application with WAR Packaging Example

---

## 📌 **Project Overview**

- **Project Name:** `maven-webapp`
- **Functionality:** A simple Java web application that displays a "Hello, World!" message using a Servlet.
- **Tech Stack:** Java 17+, Servlet API, JSP
- **Build Tool:** Maven
- **Packaging:** WAR (to deploy to a Servlet container like Tomcat or Jetty)

---

## 🗂️ **Project Structure**

```
maven-webapp/
├── pom.xml
└── src/
    ├── main/
    │   ├── java/
    │   │   └── com/example/webapp/
    │   │       └── HelloServlet.java
    │   ├── resources/
    │   └── webapp/
    │       ├── WEB-INF/
    │       │   └── web.xml
    │       └── index.jsp
    └── test/
        └── java/
            └── com/example/webapp/
                └── HelloServletTest.java
```

---

## 📄 **pom.xml**

The `pom.xml` file configures Maven to build the WAR package and includes necessary dependencies for the Servlet API and JSP.

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>maven-webapp</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>war</packaging>

    <name>Maven Web Application</name>
    <description>A simple Java web application with Maven WAR packaging</description>

    <properties>
        <java.version>17</java.version>
    </properties>

    <dependencies>
        <!-- Servlet API for Servlet-based web applications -->
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>4.0.1</version>
            <scope>provided</scope>
        </dependency>

        <!-- JSP support (if using JSP in webapp) -->
        <dependency>
            <groupId>org.apache.jasper</groupId>
            <artifactId>apache-jsp</artifactId>
            <version>2.3.3</version>
            <scope>provided</scope>
        </dependency>

        <!-- JUnit for testing -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-api</artifactId>
            <version>5.7.0</version>
            <scope>test</scope>
        </dependency>

        <!-- Tomcat Embed for running the application in an embedded container (optional) -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-tomcat</artifactId>
            <scope>provided</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <!-- WAR packaging plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-war-plugin</artifactId>
                <version>3.3.1</version>
            </plugin>

            <!-- Maven compiler plugin to ensure Java 17 -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>17</source>
                    <target>17</target>
                </configuration>
            </plugin>
        </plugins>
    </build>

</project>
```

---

## 🔹 **Explanation of Key Elements in `pom.xml`**

- **Packaging Type:**  
  `<packaging>war</packaging>` specifies that the output artifact will be a WAR file.

- **Dependencies:**  
  - `javax.servlet-api`: The Servlet API required for building Java-based web applications.
  - `apache-jsp`: Provides JSP support for the application.
  - `spring-boot-starter-tomcat`: If you want to embed Tomcat for development purposes (this is optional if you only want to deploy to an external server).
  - `JUnit`: For testing the servlet behavior.

- **Plugins:**  
  - `maven-war-plugin`: Ensures Maven packages the application as a WAR file.
  - `maven-compiler-plugin`: Ensures Java 17 is used to compile the source code.

---

## 🔹 **`HelloServlet.java` (Servlet)**

This Servlet responds with a "Hello, World!" message when accessed.

```java
package com.example.webapp;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import java.io.IOException;
import java.io.PrintWriter;

@WebServlet("/hello")
public class HelloServlet extends javax.servlet.http.HttpServlet {
    @Override
    protected void doGet(javax.servlet.http.HttpServletRequest req, javax.servlet.http.HttpServletResponse resp) throws ServletException, IOException {
        resp.setContentType("text/html");
        PrintWriter out = resp.getWriter();
        out.println("<html><body>");
        out.println("<h1>Hello, World from Servlet!</h1>");
        out.println("</body></html>");
    }
}
```

- **`@WebServlet("/hello")`** annotation: Registers the servlet at the `/hello` URL pattern.
- The servlet responds to GET requests by sending an HTML page with a "Hello, World!" message.

---

## 🔹 **`web.xml` (Deployment Descriptor)**

The `web.xml` file defines the servlet configuration. It maps the servlet class to a URL pattern.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://java.sun.com/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://java.sun.com/xml/ns/javaee
                             http://java.sun.com/xml/ns/javaee/web-app_4_0.xsd"
         version="4.0">

    <display-name>Maven Web Application</display-name>

    <servlet>
        <servlet-name>HelloServlet</servlet-name>
        <servlet-class>com.example.webapp.HelloServlet</servlet-class>
    </servlet>

    <servlet-mapping>
        <servlet-name>HelloServlet</servlet-name>
        <url-pattern>/hello</url-pattern>
    </servlet-mapping>

</web-app>
```

- **`<servlet>`**: Defines the servlet class and name.
- **`<servlet-mapping>`**: Maps the servlet to the `/hello` URL pattern.

---

## 🔹 **`index.jsp` (JSP)**

`index.jsp` is a basic JSP file that provides a link to the `/hello` servlet.

```jsp
<html>
<head>
    <title>Welcome to Maven Web Application</title>
</head>
<body>
    <h1>Welcome to the Maven Web Application!</h1>
    <a href="hello">Go to Hello Servlet</a>
</body>
</html>
```

This JSP file is served as the main page of the application.

---

## 🛠️ **Build & Run the Web Application**

### 1. **Build the Project**
To compile and package the application into a WAR file, run:

```bash
mvn clean package
```

This will create a `target/maven-webapp-1.0-SNAPSHOT.war` file.

### 2. **Deploy to Tomcat (or another Servlet container)**

- If you have Tomcat installed, you can copy the WAR file to the `webapps/` directory of Tomcat.
- Alternatively, you can deploy it using Maven with the `tomcat7:deploy` goal (if configured).

### 3. **Run the Application**

You can visit the application by accessing the following URLs in your browser:

- `http://localhost:8080/maven-webapp/` — The `index.jsp` page.
- `http://localhost:8080/maven-webapp/hello` — The `HelloServlet`.

---

## 🎯 **Testing**

For testing the servlet, you could write a simple unit test that verifies the servlet's response, for example, using **MockMvc** (from Spring Test framework).

---

## 🎁 Extras

1. **Tomcat Embedded (optional):**
   If you want to run the application using **embedded Tomcat** (instead of an external server), you could configure the `spring-boot-starter-tomcat` dependency and Spring Boot integration.

2. **Additional Configurations:**  
   You can add more servlets, JSP files, and static resources (CSS, JavaScript) inside the `webapp` folder.

---

Would you like further explanations on the Maven lifecycle, or help with deploying it to a real Tomcat server or integrating with Spring Boot? Let me know!
