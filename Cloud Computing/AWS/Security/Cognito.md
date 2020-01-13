# AWS Cognito

# Learn about OAuth2 and OpenID First
* [Youtube OAuth Tutorial](https://www.youtube.com/watch?v=996OiexHze0)
* [Youtube OAuth Tutorial](https://www.youtube.com/watch?v=lwaudf2h8FY)
* [Youtube OAuth Tutorial](https://www.youtube.com/watch?v=BdKmZ7mPNns)
* [Youtube OAuth Tutorial](https://www.youtube.com/watch?v=GyCL8AJUhww)
* [OAuth2 Home page](https://oauth.net/2/)
* [RFC6749 OAuth2](https://tools.ietf.org/html/rfc6749)
* [Wiki OAuth Page](https://en.wikipedia.org/wiki/OAuth)
* [Wiki OpenID Page](https://en.wikipedia.org/wiki/OpenID)
* [Qick Reference](https://medium.com/@robert.broeckelmann/saml2-vs-jwt-understanding-oauth2-4abde9e7ec8b)
* [OpenID detailed information](https://openid.net/connect/)

# JSon Web Tokens (JWT)

* [JWT Tutorial](https://www.youtube.com/watch?v=soGRyl9ztjI)
The Above Tutorial discusses both
* Session Tokens
* JSon Web Token (JWT)

This allows saving application context, or user session information to be maintained using HTTP(S) that is stateless request and response. Session ID may be saved in Cookies, or using HTTP posted with each request. The user session information is generally saved in the server memory. This works fine as long as the application deals with a single server, or routed to a single server.

Ues of Sticky session with load balancer is used by most data centers. All request from that specific user is routed to that specific server. But if the server is going down the user will lose the session. Also, this may not be that scaleable.

Another to fix this use a shared cache (e.g. Radis) across all servers. The Radis becommes a single point of failure.

JWT is created to fix the shoort commings of Session ID regarding the single sever.

* [Structure of JWT](https://www.youtube.com/watch?v=_XbXkVdoG_0)
* [Terms in Oauth](https://www.youtube.com/watch?v=3pZ3Nh8tgTE)
* [OAuth explained](https://www.youtube.com/watch?v=t4-416mg6iU)
* [oAuth Flow and terminilogy](https://www.youtube.com/watch?v=3pZ3Nh8tgTE)

# OAuth and OpenID used by AWS Cognito

* [AWS Cognito](https://www.youtube.com/watch?v=OAR4ZHP8DEg)
* [AWS  Authantication in Serverless env](https://www.youtube.com/watch?v=VZqG7HjT2AQ)
