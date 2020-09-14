## Express

**Express Routing**

  - Event driven system
    
    - `app.get('/thing', (req, res) => {})`

    - When a get event happens in our server on "/thing", run this function

  - The request object

    - `(req, ...)`

    - /:parameters

      - `app.get('/api/: thing', ...)` = `req.params.thing`

  - Query strings

    - `http://server/route?ball=round` = `req.query.ball`

  - The response object

    - `(..., res)`

    - Responsible for sending data back to the browser

    - Has methods like `send()` and `status()` that Express uses to format the output to the browser properly

      - Sends Headers

        - Cookies

        - Status Codes

  **Express Middleware**

  - What does it do?

    - A series f functions that the request "goes through"

    - Each function receives `request`, `response`, and `next` as parameters

    - Types of middleware: Application and Route

    - Application Middleware

      - Error handling

      - Bringing in other routes

      - Applies defaults

      - JSON, body and form parsing

      - Runs on every request

    - Route Middleware

      - Dealing with specific things for a route

      - Generally, things many routes would participate in

        - Are you logged in?

        - What's your IP?

        - Have we seen you here before?

    - How can we take advantage?

      - Logging

      - Dynamic Model Loading

      - Browser, Location, User specific content

      - Consistent Data Transition/Modeling/Preparation (Pre-Render)

  **Modularization & Separation of Concerns**

  - Modularizing your code into logical chunks

  - Each thing should do the thing its best at

  - Move files around till they feel right

  **CRUD Operatios with REST and Express**

  - CREATE

    - `app.post('/resource')`

  - READ

    - `app.get('/resource')`

  - UPDATE

    - `app.put('/resource/:id')`

  - DELETE (NOTE: The reading had "DESTROY" but I believe the correct term is "DELETE")

    - `app.get('/resource/:id')`

  **Server Testing**

  - Generally, avoid starting the actual server for testing

  - Instead, export your server as a module in a library

  - Then you can use `supertest` to run your tests

    - This will hit your routes as though your server was running, without actually starting it

    - That's one less thing to go wrong (eleminate variables when testing)

  - Additionally, you can wrap `superagent` in a module and do more testing with it

  **Test Pyramid**

  - Server Testing crosses boundaries

    - Units: Server Internal Functions

      - Mock any integrations (like data fetching)

    - Integration: How it connects to other services

      - Really connect to other services (hard dependencies)

    - Acceptance

      - The server might be a dependency of some other test
