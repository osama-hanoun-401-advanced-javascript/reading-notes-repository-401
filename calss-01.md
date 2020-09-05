## Node Ecosystem, TDD, CI/CD

## Sources:

[NPM Documentation](https://docs.npmjs.com/packages-and-modules/)

[Understanding Module Exports and Exports in Node.js](https://www.sitepoint.com/understanding-module-exports-exports-node-js/)

[Node.js What is NPM](https://nodejs.org/en/knowledge/getting-started/npm/what-is-npm/)

[Dictionary.com](https://www.dictionary.com/)


- Why would you want to run JavaScript code outside of a browser?
  - Node.js was created to allow JavaScript to run in the terminal, for back-end, or server-side programming. So, for this reason you nay need to run JS outside of a browser.

- What is the difference between a module and a package?
  - A package is a file or directory that is described by a package.json file. A package must contain a package.json file.

  - A module is any file or directory in the node_modules directory that can be loaded byt the Node.js require() function

- What does the node package manager do?
  - NPM (Node Package Manager) is a command line tool that installs, updates, or uninstalls Node.js packages in applications. It's also an online repository for open-source Node.js projects.

- Provide code snippets showing 3 different ways to export a function from a node module.
  - The Asynchronous Module Definition format is used in browsers and uses a `define` finction to define modules.

  - The CommonJS format is used in Node.js and uses `require` and `module.exports` to define dependencies and modules. The npm ecosystem is built on this format.

  - The ES Module format. As of ES6, JavaScript supports a native module format, which uses an `export` keyword to export a module's public API and an `import` keyword to import it.

## Vocabulary Terms:

**Ecosystem:** A collection of software projects, which are developed and co-evolve in the same environment. The environment can be organizational (a company), social (an open-source community), or technical (like NPM). [Wikipedia](https://en.wikipedia.org/wiki/Software_ecosystem#:~:text=In%20the%20context%20of%20software,technical%20(the%20Ruby%20ecosystem).)

**Node.js:** An asynchronous event-driven javaScript runtime.

**V8 Engine:** JavaScript environment used in Google Chrome

**Module:** A module is any file or directory in the node_modules directory that can be loaded byt the Node.js require() function

**Package:** A package is a file or directory that is described by a package.json file. A package must contain a package.json file.

**Node Package Manager (NPM):** A command line tool that installs, updates, or uninstalls Node.js packages in applications. It's also an online repository for open-source Node.js projects.

**Server:** a computer or computer program which manages access to a centralized resource or service in a network.

**Environment:** A combination of software and hardware in a computer.

**Interpreter:** A program that directly executes instruction written in a programming or scripting language, without requiring them previously to have been compiled into a machine language program. [Wikipedia](https://en.wikipedia.org/wiki/Interpreter_(computing)#:~:text=In%20computer%20science%2C%20an%20interpreter,into%20a%20machine%20language%20program.)

**Compiler:** A program that translates computer code written in one programming language (the source language) into another language (the target language). [Wikipedia](https://en.wikipedia.org/wiki/Compiler#:~:text=A%20compiler%20is%20a%20computer,language%20(the%20target%20language).&text=A%20program%20that%20translates%20between,to%2Dsource%20compiler%20or%20transcompiler.)
