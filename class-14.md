## Access Control (ACL)

**Access Controls**

- Access Controls are the selective restriction of resources. Access Controls are implemented everywhere in computer systems. UNIX files have read, write, and execute permissions assigned to owners, groups, and everyone else. Websites have limited access to pages based on the credentials of a user. APIs restrict access to internal and external developers differently.

- In our RESTful APIs, it is important to limit access to clients based on credentials. This means a user should not be able to delete another user's resource, unless given permission to do so. Limiting what actions a user can perform on a given resource is called Access Control. A user can be given a token at signup and login, and that user can pass that token back to the server on requests with limited access controls. Once the server parses the token, it can determine if the user is authorized to perform the request.

**Application Flow and Access Control**

- Applications of all types have varying degrees of access based on user type and UI requirements.

- A CMS (Contact Management System) might:

  - Allow **admin** users to create categories, content, manage user accounts, and run reports

  - Allow **editor** users to creade, edit, and delete existing content, but not see or manage user accounts

  - Allow **guest** users to access (read) content

  - Allow **user** users (logged in users) to access (read) content and apply a thumbs-up/down to content, but not change the actual content.

- Each of these constraints will have to be handled on both the backend and the front end of your application stack.

**Back End (API Layer)**

- Manage the login cycle with the front-end application

- Maintain the User database

- Maintain roles for each user

- Authenticate users (basic and bearer)

- Create, manage, and apply Role Based Access Controls

- Maintain and reference their capabilities, based on their role

- Restrict access to features (like routes) based on capabilities

  - Express Middleware could be used to restrict access to routes

  - Mongoose Middleware/Hooks could be used to restrict access to business logic

**Front End (Client Layer)**

- Initiate the login process

- Store login tokens as cookies

- Manage login state, capabilities

- Control physical & visual access (hide/show/alter) to components based on RBAC (Role Based Access Control) rules
