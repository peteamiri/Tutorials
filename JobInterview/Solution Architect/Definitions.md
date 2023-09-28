## Authantication secction

### OAuth2.0

OAuth 2.0 (Open Authorization 2.0) an industry-standard protocol for authorization that allows third-party applications to access a user's data or perform actions on their behalf without the need to share the user's credentials, like usernames and passwords. OAuth 2.0 is widely used in the context of secure authentication and authorization in various applications, including web and mobile apps, APIs (Application Programming Interfaces), and IoT (Internet of Things) devices. Here are the key concepts and components of OAuth 2.0:

1. **Resource Owner:** The resource owner is an entity (usually a user) who owns the data, content, or resources being protected. For example, a user's photos on a social media platform.

1. **Client:** The client is an application or service that seeks access to the resource owner's data. It could be a mobile app, a web app, or even a server-based application.

1. **Authorization Server:** The authorization server is responsible for authenticating the resource owner and obtaining their consent. It issues **access tokens** to authorized clients.

1. **Resource Server:** This is the server where the protected resources are stored and managed. It verifies the access tokens and serves the protected resources.

1. **Access Token:** An access token is a credential that the client presents to the resource server when requesting access to protected resources. It acts as proof that the resource owner has granted permission for the client to access their data.

1. **Scope:** Scopes define the specific permissions or access levels granted to the client. For example, a scope might specify read-only access to a user's email or full access to their calendar.

The OAuth 2.0 flow typically involves the following steps:

1. **Authorization Request:** The client initiates the process by sending an authorization request to the authorization server, including details like its identity and requested scope.

1. **User Consent:** The authorization server authenticates the resource owner and seeks their consent to grant access to the client. The resource owner may be prompted to log in or confirm the requested permissions.

1. **Authorization Grant:** After receiving consent, the authorization server issues an authorization grant to the client. The type of grant depends on the specific OAuth 2.0 flow being used.

1. **Access Token Request:** The client then exchanges the authorization grant for an access token by sending a request to the authorization server.

1. **Access Token Issuance:** Upon successful verification, the authorization server issues an access token to the client.

1. **Accessing Resources:** The client uses the access token to access protected resources on the resource server.

1. **Resource Server Validation:** The resource server validates the access token, ensuring it's not expired and has the necessary scopes to perform the requested action.

OAuth 2.0 is a flexible and widely adopted protocol used to provide secure access to resources while maintaining user privacy. It's used in scenarios such as social media logins, single sign-on (SSO), and API authorization. Different OAuth 2.0 flows exist to accommodate various use cases, including Authorization Code Flow, Implicit Flow, Client Credentials Flow, and Resource Owner Password Credentials Flow. The choice of flow depends on the specific requirements of the application.

### See more for more details

* [OAuth2.0 Home](https://oauth.net/2/)
* [Auth2.0 Information](https://auth0.com/intro-to-iam/what-is-oauth-2)
* [Auth2.0 Integration](https://auth0.com/docs/)
* [RFC6749](https://datatracker.ietf.org/doc/html/rfc6749)




### OIDC
### SAML
### WS-Fderation
### JWT
### MFA
### SSO
### LDAP
### Kerberos
### MTLM

## Active Directory Terms

* **Domain**:
* **Domainn Controller**:
*
