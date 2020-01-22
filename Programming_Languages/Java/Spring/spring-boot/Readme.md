# Spring Boot

* [Spring Boot Manual](https://docs.spring.io/spring-boot/docs/current/reference/html/)
* [Spring Boot Getting Started](https://spring.io/guides/gs/spring-boot/)
* [Vrious Youtube Tutorials](https://www.youtube.com/channel/UCbz69gWlMmsIn-jiIm6mGfg/videos)

# Spring Boot creating MicroServvice
The followings are steps to create a MicroService. 

1. Generaate the Code using initialzr.
   * add web applications
   * add spring security (JWT, OAuth, OpenID Connect)
2. Add Spring Controller
  * Create a class
  * Add `@RestController` to the class at class level
  * Add `@RequestMapping` at the method level
    - define `method = RequestMethod.POST`
    - define `value = "/register"` for URL
    - add `produces = APPLICATION_JSON_VALUE` to provide response type.
    - add `@RequestBody ClassName ObjectName` as the input variable
3. Create data value Object
4. Create Database connection
   - Add hibernate
5. Add Business rules
   - Add Drool
6. Add Dockerfile and copy the jar into the Image
7. push the image into the repository

The following code is a sample RestController Class.

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
