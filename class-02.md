## Classes, Inheritance, Functional Programming

## Sources

[Stack Overflow](https://stackoverflow.com/)

[Toptal](https://www.toptal.com/)

[Knowledge Hut](https://www.knowledgehut.com/)

[Jest Docs](https://jestjs.io/docs)

[JavaScript Info](https://javascript.info/)

[Medium](https://medium.com/)

[W3 Schools](https://www.w3schools.com/)

- Name 3 advantages to Test Driven Development
  - TDD maximizes the possibility of developing the best quality product fulfilling the communicated needs of all stakeholders
  - TDD process gets fit into the customer-centric agile methodology. The iteration for quality improvement is defined as the incorporation of new functionality against the model set of traditional practices or problem statements.
  - The streamlined TDD process helps the project development team members to improve their delivering capability because of providing the immediate feedback on the developed components.

- In what case would you need to use `beforeEach()` or `afterEach()` in a test suite?
  - If you have a repeating setup for a number of tests, you can use `beforeEach` and `afterEach` to denote that a specific method needs to be called before each of the tests, and a specific method that needs to be called after each of the tests.

- What is one downside of Test Driven Development
  - TDD is a big time investment. For the simple case, you lose about 20% of the actual implementation.

- What’s the primary difference between ES6 Classes and Constructor/Prototype Classes?
  - A class defines a *type* which can be instantiated at runtime, whereas a prototype is itself an object instance.

- Name a use case for a static method
  - Usually, static methods are used to implement functions that belong to the class, but not to any particular object of it.

- Write an example of a Higher Order function and describe the use case it solves
  - `.map()` is a higher order function because it takes in a function as an argument or returns a function as a result.

## Vocabulary

**functional programming**
  - Functional programming languages are specially designed to handle symbolic computation and list processing applications.

**pure function**
  - A pure function’s return value is based only on its inputs and has no other dependencies or effects on the overall program.

**higher-order function**
  - A function that can take another function as an argument or returns a function as a result.

**immutable state**
  - An object whos state cannot be modified after it is created.

**object**
  - Objects are containers for named values called properties or methods.

**object-oriented programming (OOP)**
  - OOP refers to a type of programming in which we define the data-type of a data-structure, and also the types of operations (methods) that can be applied to the data-structure.

**class**
  - A class is a type of function, but instead of using the keyword `function` to initiate it, we use the keyword `class`, and the properties are assigned inside a `constructor()` method.

**prototype**
  - All JavaScript objects inherit properties and methods from a prototype.

**super**
  - The super keyword is used to access and call functions on an object's parent.

**inheritance**
  - In simple terms, inheritance is the concept of one thing gaining the properties or behaviors of something else. To say A inherits from B, is saying that A is a type of B.

**constructor**
  - A constructor is a function that creates an instance of an object.

**instance**
  - An instance means a reference to an object created by the `new` keyword.

**context**
  - Refers to the scope of `this`.

**this**
  - Refers to the object it belongs to.

**Test Driven Development (TDD)**
  - TDD is the act of first deciding what you want your program to do, formulating a failing test, then writing the code to make that test pass.

**Jest**
  - Jest is a JS library for creating, running, and structuring tests.

**Continuous Integration (CI)**
  - The practice of creating frequent and isolated changes in code, which are immediately tested and reported on when they are added to a larger code base.
  
**unit test**
  - A unit test is designed to test an individual function or library in your code.
