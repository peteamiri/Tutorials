# MicroService Security

* [Starting Point](https://www.youtube.com/watch?v=wpA0N7kHaDo)

* You need to authorize and authanticate for each service call (Session independent).
  - Authorization
  - Authantication

## Best Practicies

### Defence in Dept

* Provide a layers of security.
* Variation of security,

### Session Afinity and sesssion management (User base interactions)
* Session infomration is saved on Server Side
  - Single Server save all the infomration.
    - Not scalebale, and single point of failure.
  - Session infomration is shared across servers
    - Cookies, store the Session tokens.
    - Seission (HTTP Post) ID/Token
      - Sticky Session session is stored on a single server
        - No useful when there are autoscaling and complex routiings
      - Storing session information in Memory and session information is accessed the in-memory cluster.
        - Complex in setting up
      - Storing Session informaton in database and session informaiton is extraaced from database each time
        - Performance impacts.

* Session information is saved on client side
* Mainaining user session information including authorization and authantication

  - Java Web Token (JWT) : Store session information in an envlop add header and footer, encrypt the envlop and pass that to user to maintain this informaition.

### API Gateway

* Is a layer that directly deals with client application to protect the Service layer. This layer also perform authorization and authantication.

### Distributed Tracing, monitoring, and logging

* Continious loging and monitoring.
* Logging proceess to identify the failure and its cause, and location.
