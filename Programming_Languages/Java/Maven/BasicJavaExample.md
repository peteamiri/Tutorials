Sure! Here's a **detailed example** of using **Maven** to create and manage a **basic Java project**. This includes:

- Folder structure  
- `pom.xml` setup  
- A simple Java class  
- Unit testing with JUnit  
- Build and run commands  

---

# 📦 **Basic Java Project with Maven**

---

## 🗂️ Project Structure

```
basic-java-maven/
├── pom.xml
└── src/
    ├── main/
    │   └── java/
    │       └── com/
    │           └── example/
    │               └── App.java
    └── test/
        └── java/
            └── com/
                └── example/
                    └── AppTest.java
```

---

## 📄 `pom.xml`

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>basic-java-maven</artifactId>
    <version>1.0-SNAPSHOT</version>

    <name>Basic Java Maven</name>
    <description>A simple Java project using Maven</description>

    <properties>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
    </properties>

    <dependencies>
        <!-- JUnit for testing -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.13.2</version>
            <scope>test</scope>
        </dependency>
    </dependencies>

</project>
```

---

## 🧠 Explanation of Key Elements in `pom.xml`

| Tag | Purpose |
|-----|---------|
| `<groupId>` | Uniquely identifies your project’s organization (like a namespace) |
| `<artifactId>` | The name of your project/module |
| `<version>` | The project version |
| `<dependencies>` | Declares external libraries (e.g., JUnit for testing) |
| `<properties>` | Set Java version compatibility |

---

## 🔹 `App.java` (Main Class)

```java
package com.example;

public class App {
    public static void main(String[] args) {
        System.out.println("Hello, Maven!");
    }

    public static int add(int a, int b) {
        return a + b;
    }
}
```

---

## ✅ `AppTest.java` (JUnit Test)

```java
package com.example;

import org.junit.Test;
import static org.junit.Assert.*;

public class AppTest {

    @Test
    public void testAddition() {
        assertEquals(5, App.add(2, 3));
    }
}
```

---

## 🛠️ Maven Commands

### 1. **Compile the Project**
```bash
mvn compile
```

### 2. **Run Unit Tests**
```bash
mvn test
```

### 3. **Package into a JAR**
```bash
mvn package
```
Output:
```
target/basic-java-maven-1.0-SNAPSHOT.jar
```

### 4. **Run the App (Using Exec Plugin)**

To run the app via Maven, add the **Exec Plugin** to your `pom.xml`:

```xml
<build>
  <plugins>
    <plugin>
      <groupId>org.codehaus.mojo</groupId>
      <artifactId>exec-maven-plugin</artifactId>
      <version>3.1.0</version>
      <configuration>
        <mainClass>com.example.App</mainClass>
      </configuration>
    </plugin>
  </plugins>
</build>
```

Then run:
```bash
mvn exec:java
```

---

## 📦 Build Output Directory

After packaging:
```
target/
├── classes/
├── test-classes/
├── basic-java-maven-1.0-SNAPSHOT.jar
├── surefire-reports/
└── ...
```

---

## 🎯 Summary

This project demonstrates how Maven:

- Organizes a Java project with standard directory layout
- Manages dependencies (JUnit)
- Builds, tests, and packages Java code
- Runs code via plugins

---

Would you like this packaged as a downloadable ZIP, or should I walk you through converting this into a multi-module project or integrating with an IDE (e.g., IntelliJ or Eclipse)?
