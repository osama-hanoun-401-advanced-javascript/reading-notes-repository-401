## OAUTH

**OAuth 2.0**

  - If you’ve ever seen and/or used the pop-up dialog box to “Login With Google” (or Facebook, or Github), you’ve used OAuth as a client (user). What’s really going on? Officially, OAuth is “an open standard for access delegation” … In other words, OAuth serves as a way to give users the ability to grant application access to services, without giving the application their password.

  - When you "Login with Google", you've actually given the application (or website) the keys to some of your personal information and access levels at Google. Generally, sites and apps use this as a simplified way of having you login through one system. But if they've asked for it (and you agreed to it), the application can also do things such as create or delete documents or access other services "as you". When you "Login with Google" the application that requested that, for all intents and purposes, **Is You**. Which means it can effectively do things at Google (or Facebook, or wherever) as though it was you at the keyboard.

**How does OAuth work?**

  - Through a series of "handshakes", an application such as an Express Web Server asks the user if it's ok to login as them at some remote service, an then begines the process of authentication and access

    1. Application spawns the "Login Using xxx" window, asking for specific permissions.

    2. User agrees to allow this to happen.

    3. Remote service (i.e.: Google) contacts the application with a one-time-use `Code`.

    4. The application calls back to a special address on the remote service to exchange that `Code` for a `Token`.

    5. Once the token has been granted, the application will then be able to contact the remote service, using that Token to access information on behalf of the user.

    - The `token` is the user.

**Access Code**

  - First the client need to grant the application permission. To do this you need to provide an `<a>` tag that will take them to the service's authorization page. This `<a>` tag should pass the following information through a query string to the authorization server. Every service is slightly different in their specific requirements, but in some form or another, variables lie these are part of this initial request:

    - `response_type=code` indicates that your server wants to receive an authorization code

    - `client_id=<your client id>` tells the authorization server which app the user is granting access to

    - `redirect_uri=<your redirect uri>` tells the auth server which server endpoint to redirect to

    - `scope=<list of scopes>` tells the auth server what you want the user to give access to

    - `state=<anything you want>` a place you can store info to pass to your server if you want.

**Access Token**

  - If the users grants access to the application, the authorization server will redirect to a provided redirect URI callback with a “code”. Once you have this code, you can exchange it for an access token by making a `POST` request to the authorization server and providing the following information:

    - `grant_type=authorization_code`

    - `code=<the code you received>`

    - `redirect_uri=REDIRECT_URI` must be the same as the redirect URI your client provided

    - `client_id=<your client id>` tells the auth server which application is making the requests

    - `client_secret=<your client secret>` authenticates that the application making the request is the application registered with the `client_id`

    - Once you get an access token, you can use it to make API calls to the service on behalf of that user
