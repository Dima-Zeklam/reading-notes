# Authentication

![User Authentication](https://www.cisco.com/c/dam/assets/swa/img/anchor-info/what-is-user-authentication-628x353.png)

### What is OAuth?
OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential.
### Give an example of what using OAuth would look like.
 OAuth as similar to a **car’s valet key**, which can be used to allow a valet to temporarily drive and park a car, but it doesn’t allow the holder full, unlimited access like a regular key. Instead the car can only be driven a few miles, can’t access the trunk or locked glove box, and can have many other limitations.

### How does OAuth work? What are the steps that it takes to authenticate the user?

1. The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.
2. The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.
3. The first site gives this token and secret to the initiating user’s client software.
4. The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).
5. If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.
6. The user approves (or their software silently approves) a particular transaction type at the first website.
7. The user is given an approved access token (notice it’s no longer a request token).
8. The user gives the approved access token to the first website.
9. The first website gives the access token to the second website as proof of authentication on behalf of the user.
10. The second website lets the first website access their site on behalf of the user.
11. The user sees a successfully completed transaction occurring.

### What is OpenID?


![OpenID](https://upload.wikimedia.org/wikipedia/commons/thumb/3/32/OpenIDvs.Pseudo-AuthenticationusingOAuth.svg/512px-OpenIDvs.Pseudo-AuthenticationusingOAuth.svg.png)

is an open standard and decentralized authentication protocol. Promoted by the non-profit OpenID Foundation, it allows users to be authenticated by cooperating sites (known as relying parties, or RP) using a third-party service, eliminating the need for webmasters to provide their own ad hoc login systems, and allowing users to log into multiple unrelated websites without having to have a separate identity and password for each

### What is the difference between authorization and authentication?
![authorization vs authentication](https://aboutssl.org/wp-content/uploads/2020/06/authentication-vs-authorization.svg)

Authentication | Authorization
---------------|---------------
Determines whether users are who they claim to be|	Determines what users can and cannot access
Challenges the user to validate credentials (for example, through passwords, answers to security questions, or facial recognition) |	Verifies whether access is allowed through policies and rules
Usually done before authorization |	Usually done after successful authentication
Generally, transmits info through an ID Token |	Generally, transmits info through an Access Token
Generally governed by the OpenID Connect (OIDC) protocol |	Generally governed by the OAuth 2.0 framework
Example: Employees in a company are required to authenticate through the network before accessing their company email |Example: After an employee successfully authenticates, the system determines what information the employees are allowed to access

### What is Authorization Code Flow?
Because regular web apps are server-side apps where the source code is not publicly exposed, they can use the Authorization Code Flow, which exchanges an Authorization Code for a token.

### What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
During authentication, mobile and native applications can use the Authorization Code Flow, but they require additional security. Additionally, single-page apps have special challenges. To mitigate these, OAuth 2.0 provides a version of the Authorization Code Flow which makes use of a Proof Key for Code Exchange (PKCE).

### What is Implicit Flow with Form Post?
As an alternative to the Authorization Code Flow, OAuth 2.0 provides the Implicit Flow, which is intended for Public Clients, or applications which are unable to securely store Client Secrets.
### What is Client Credentials Flow?
With machine-to-machine (M2M) applications, such as CLIs, daemons, or services running on your back-end, the system authenticates and authorizes the app rather than a user. For this scenario, typical authentication schemes like username + password or social logins don't make sense. 

### What is Device Authorization Flow?
![Device Authorization Flow](https://images.ctfassets.net/cdy7uua7fh8z/1A6jpG3W1H6SC9ZK92NyKd/40af53209f90a7c392f621f329fb4424/auth-sequence-device-auth.png)

### What is Resource Owner Password Flow?
highly-trusted applications can use the Resource Owner Password Flow, which requests that users provide credentials (username and password), typically using an interactive form. The Resource Owner Password Flow should only be used when redirect-based flows (like the Authorization Code Flow) cannot be used.

## Things I want to know more about
* Dark web
* SSL/TLS protocol

