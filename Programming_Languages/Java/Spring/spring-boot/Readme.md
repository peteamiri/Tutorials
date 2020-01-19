# Spring Boot

* [Spring Boot Manual](https://docs.spring.io/spring-boot/docs/current/reference/html/)
* [Spring Boot Getting Started](https://spring.io/guides/gs/spring-boot/)
* [Vrious Youtube Tutorials](https://www.youtube.com/channel/UCbz69gWlMmsIn-jiIm6mGfg/videos)

# Spring Boot creating MicroServvice

1. Generaate the Code using initialzr.
2. Add Spring Controller
3. Create data value
4. Create Database connection
5. Add Business rules
6. Add Dockerfile and copy the jar into the Image
7. push the image into the repository

```
@RestController
public class RegistrationController {

    @RequestMapping(method = RequestMethod.POST,
                    value = "/register",
                    produces = APPLICATION_JSON_VALUE)
    public UserData register(@RequestBody User user) {
        ...
        if(usernameAlreadyExists) {
            throw new IllegalArgumentException("error.username");
        }
        ...
        return new UserData(...);
    }

    @ExceptionHandler
    void handleIllegalArgumentException(
                      IllegalArgumentException e,
                      HttpServletResponse response) throws IOException {

        response.sendError(HttpStatus.BAD_REQUEST.value());

    }
}
```
