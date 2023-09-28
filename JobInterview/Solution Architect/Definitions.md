## Authantication secction

* **OAuth2.0**:OAuth 2.0 (Open Authorization 2.0) is an industry-standard protocol used for authorization and secure access to web-based and mobile applications. It provides a way for one application to allow another application or service to access its resources on behalf of a user without sharing the user's credentials (such as passwords) directly.

OAuth 2.0 is commonly used for scenarios where you want to grant a third-party application limited access to your resources. This is often seen in the context of social media logins or allowing third-party services to access your data on platforms like Google, Facebook, or GitHub.

Key components and roles in the OAuth 2.0 protocol include:

Resource Owner: This is the user who owns the data or resources. For example, if you're using OAuth 2.0 to access your Google Drive files from a third-party application, you are the resource owner.

Client: The client is the third-party application or service that wants to access the resource owner's data. The client must be registered with the authorization server.

Authorization Server: The authorization server is responsible for authenticating the resource owner, handling user consent, and issuing access tokens to authorized clients. It verifies the client's identity and the resource owner's permissions.

Resource Server: This is the server where the protected resources are hosted. It's the server that the client wants to access on behalf of the resource owner. In the Google Drive example, Google's servers are the resource server.

Access Token: An access token is a credential that the client uses to access the resource server on behalf of the resource owner. It's a short-lived token that grants specific permissions. OAuth 2.0 access tokens can be bearer tokens or JWTs (JSON Web Tokens).

Scope: Scopes define the specific permissions or access rights requested by the client. For instance, a client might request read-only access to a user's email.

The OAuth 2.0 flow typically involves the following steps:

The client requests authorization from the resource owner by redirecting them to the authorization server.

The resource owner authenticates themselves and grants permission to the client.

The authorization server issues an access token to the client.

The client uses the access token to access the protected resources on the resource server.

The resource server validates the access token and, if valid, provides the requested data.

OAuth 2.0 is a flexible and widely adopted protocol that's used in various applications and scenarios where secure, delegated access to resources is required. It's essential for ensuring user privacy and security when third-party applications need access to a user's data without exposing sensitive credentials.

* **OIDC**:
* **SAML**:
* **WS-Fderation**:
* **JWT**:
* **MFA**:
* **SSO**:
* **LDAP**:
* **Kerberos**:
* **MTLM**:

## Active Directory Terms

* **Domain**:
* **Domainn Controller**:
*
