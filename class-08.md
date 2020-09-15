# Express Routing & Connected API

### What is a benefit to using express.Router()?

   * express. Router() is use multiple times to define groups of routes. route used as middleware to process requests. route used as middleware to validate parameters using

### When I say that top-down order matters in Express, what does that mean?

   * Express read files from top to down means, for instance if we put our 404 route on the top of our page and we a proper get path it will breake our code(send 404 error message) before checking the get route.

### Why do we use a model class (with create(), read(), etc.) instead of directly calling MongoDB operations (such as save(), find(), etc.) within our Express route handlers?

   * When running the handler middleware, there is a strong likelyhood that some data operation needs to take place. The handler function kicks off this asynchronous data operation by calling a model function such as create(), read(), update() or delete(). This refers to a model class built in a /models folder, utilizing a schema also defined in the /models folder. The handler then awaits this data operation to complete

### How does this change the server's role?

  - index.js - Entry Point

  - server.js - Hub, Exported Server

  - models/categories.js - Data Models

  - routes/categories.js, etc. - Rutes and Handlers
