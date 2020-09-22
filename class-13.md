## Bearer Authorization

**Bearer Authentication**

- Following a `signin` attempt, either using Basic Authentication (where your username and password are transmitted to a server) or OAuth (where there is a cumbersom handshaking/authorization process), your service is able to make a boolean decision as to the success of the attempt.

- Assuming the `signin`was successful, we can assert that it would be both more efficient and secure if the server "just knew" that the client making subsequent requests was allowed to do so.

- Rather than continually sending username+password over the internet, or undergoing the long OAuth process, we are able to use a secondary authentication method called "Bearer Token".

- Bearer Tokens are encoded JSON objects that "bear" or "contain" enough information for the server to assert that any client request that presents a valid token must have originated from a client that has previously authenticated themselves using either Basic or OAuth. Upon receiving a Bearer Token from a client, the server can decode it, inspect the JSON object inside, look up the appropriate account, and re-authenticate the user in a single lookup.

  - Bearer Tokens are sent to the user/client after the initial `signin` process has completed.

  - Clients must make every subsequent request to the server with that token, in the header

    - `Authorization: Bearer encoded.jsonwebtoken.here`

  - The server opens the token, does the re-authorization, and then grants or denies access

  - In express servers, this can be done in middleware, in conjunction with a user model

**JSON Web Tokens**

  *Adapted from* https://jwt.io/introduction/

- JSON Web Token (JWT) is an open standard that defines a compact and self-contained way for securely transmitting information between parties (servers, clients, etc.) as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.

- Although JWTs can be encrypted to also provide secrecy between parties, we will focus on signed tokens. Signed tokens can verify the integrity of the claims contained within them, while encrypted tokens hide those claims from other parties. When tokens are signed using public/private key pairs, the signature also certifies that only the party holding the private key is the one that signed it.

- **NOTE:** Signing a token does not secure its contents. They are viewable, so be careful of the information that you include in the JSON data. A properly signed token is verified. In other words, you can be assured it wasn't modified in any way during transport and you can be certain that the generator of the token was trusted (as they have the same hey that you do).

**When should you use JWTs?**

- **Authorization:** This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access the routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because if its small overhead and its ability to be easily used across different domains.

- **Information Exchange:** JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed - for example, using public/private key pairs - you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.
