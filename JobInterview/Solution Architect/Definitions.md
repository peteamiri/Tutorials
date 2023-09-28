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




### OpenID Connection (OIDC)

OpenID Connect (OIDC) is an authentication and authorization protocol **built on top of OAuth 2.0**. It's designed to facilitate secure and user-friendly authentication for web and mobile applications. OIDC provides a standardized way for applications to verify the identity of end-users and, optionally, obtain basic profile information about them. It is commonly used for single sign-on (SSO) scenarios and is widely adopted for identity management in modern web applications. Here are the key concepts and components of OIDC:

1. **Identity Provider (IdP)**: The Identity Provider is a trusted entity that verifies the identity of users and provides information about them to relying parties (applications). Popular IdPs include Google, Facebook, Microsoft Azure AD, and Okta.

Relying Party (RP): The Relying Party is the application or service that relies on the IdP to authenticate users. The RP is responsible for initiating OIDC flows and consuming user identity information.

End-User: The end-user is the person who is using the RP's application and attempting to authenticate.

ID Token: The ID Token is a JSON Web Token (JWT) that the IdP issues to the RP after a successful authentication. It contains information about the user, such as their unique identifier and, optionally, other profile attributes.

Access Token: Similar to OAuth 2.0, OIDC can also issue access tokens that the RP can use to access protected resources on behalf of the user.

Userinfo Endpoint: OIDC defines a Userinfo Endpoint that the RP can use to obtain additional user profile information, such as email address or display name, after receiving an ID Token.

The OIDC authentication flow involves the following steps:

Authentication Request: The RP initiates the authentication process by sending an authentication request to the IdP. This request typically includes the desired scope and response type, specifying what information the RP is requesting.

User Authentication: The IdP authenticates the user. This may involve username and password, multi-factor authentication, or other authentication mechanisms depending on the IdP's policies.

ID Token Issuance: After successful authentication, the IdP generates an ID Token containing information about the user and sends it back to the RP.

RP Validation: The RP validates the ID Token to ensure its authenticity, including checking the signature and expiration time.

Optional Access Token: If needed, the IdP may also issue an access token to the RP, allowing it to access resources on the user's behalf.

Userinfo Request (Optional): The RP may make an additional request to the Userinfo Endpoint to obtain more user profile information.

OIDC is widely used to enable single sign-on (SSO) experiences, where users can log in to one application and subsequently access other applications without needing to re-enter their credentials. It provides a standardized and secure way to handle user authentication and identity information, making it a valuable tool for modern web and mobile application development.

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
