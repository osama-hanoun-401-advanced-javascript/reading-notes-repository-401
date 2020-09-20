## Authentication

**User Modeling**

  - Modern web applications need to model sensitive information about their users. When a user provides an application with sensitive information, they are trusting that it will not be leaked or misused. This means that it is a developer's responsibility to store that information responsibly. Some information, like emails, user names, and addresses can be stored in plain text, as long as the database is password protected and/or behind a firewall. Other information, like a user's password, should be encrypted using a hashing algorithm before it is ever stored. This prevents anyone (including developers with database permissions) from ever getting access to their password.

  - User models that have sensitive data should **NEVER** be sent to client applications. If your application requires that users be able to read each other's personal information, create a second Profile model to hold that data and strictly limit access to the Profile model. Safely using a second model will ensure that no user will accidentally, or maliciously, gain access to sensitive information.

**Cryptography**

  - Crypography is the science which studies methods for encoding messages so that they can be read only by a person who knows the secret information required for decoding, called the key; it includes cryptanalysis, the science of decoding encrypted messages without possessing the proper key, and has several other branches.

  [GNU Collaborative International Dictionary of English](https://gcide.gnu.org.ua/)

**Hash Algorithms**

  - A Cryptographic Hash Algorithm takes a piece of data and produces a hash that is deliberately difficult to reverse. If identical data is passed into the algorithm, the same hash will always be produced. Hash algorithms are often used for checking the integrity of data.

  - In a User model, a hash password can be stored when the user signs up. When the user needs to login, they can resend their password and the server can hash the login password using the same hash algorithm. The server can then compare the hashed login password with the previously stored hashed password to determine if the user should be authenticated.

**Cypher Algorithms**

  - A Cryptographic Cypher algorithm takes a piece of data and a key and produces encrypted data. Later the encrypted data can be reversed into the original data by decrypting it using the same key.

  - User tokens can be created by associating a random unique string (tokenSeed) with a user accound and, in turn, encrypting the tokenSeed with a secret key that only the server knows. We can then send the encrypted token to a client application. When the client makes a future request they send back the token. The server can reverse the token into the tokenSeed by decrypting it with the secret key. This is because the tokenSeed was unique to the database and can be queried to produce the user who made the request.

**Basic Authorization**

  - Basic Authorization is a common method used to send a username and password in an HTTP request. The username and passowrk ar joined with a ':' then "base64 encoded" and placed after the string 'Basic'. The resulting string is set to the value of an Authorization header.

  - A Server can decode the Basic Authorization header to retrieve the username and password. If the combination is validated, the server generally responds back to the client with some sort of validation response (token or key) so that the client can re-authenticate without having to continually send the username:password combination in plain text over the internet.
