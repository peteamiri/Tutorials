# Spring

# Sprint Boot
* [Good Starting Point](https://www.youtube.com/watch?v=msXL2oDexqw&list=PLqq-6Pq4lTTbx8p2oCgcAQGQyqN8XeA1x)
* [Compliments the above tutorial](https://www.tutorialspoint.com/spring_boot/index.htm)


## what you need
* Java 8
* Spring STS
* Maven


# Step One Spring initialzr
This step you generate the project usingg maven.

* [Spring Initialzr](https://start.spring.io/)

Group is the package name,
Artifact is the project name

The Jar selection provides the imbeded Tomcat
The War selection allows you to deploy the code to the Application Server like Tomcat, Weblogic, JBoss

Import the project into the Sprting STS

## Create a Rest Controller
This is the web interface

```
  package com.tutorialspoint.demo;

  import org.springframework.boot.SpringApplication;
  import org.springframework.boot.autoconfigure.SpringBootApplication;
  import org.springframework.web.bind.annotation.RequestMapping;
  import org.springframework.web.bind.annotation.RestController;

  @RestController
  public class DemoApplication {

     @RequestMapping(value = "/")
     public String hello() {
        return "Hello World";
     }
  }
```
### Create a Business Layer

# tutorial

* [Start Here](https://www.baeldung.com/start-here)
* [Spring](https://howtodoinjava.com/spring-cloud/)
* [Spring.io](https://spring.io/)
* [Tutorial](https://www.javainuse.com/spring)
* [Tutorial-2](https://www.devglan.com/spring-cloud/spring-cloud-tutorial)
* [Spring Platform Guide](https://spring.io/guides)

## Spring Config

* [Spring Config](https://spring.io/projects/spring-cloud-config)

## Tutorials

* [Rest with Spring](https://github.com/eugenp/tutorials)
