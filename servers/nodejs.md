<h3 align="center"><a href="../table_of_contents.md">👈 Back to Table of Contents</a></h3>

---

# ✍️ Notes for "Node.js"
- ### What is it?
  - Node.js® is a JavaScript runtime built on Chrome’s V8 JavaScript engine.
  - Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google’s V8 JavaScript engine and libuv library.
  - It’s a JavaScript runtime.

---

- ### Google Chrome's V8 JavaScript Engine
  - The V8 engine is the open-source JavaScript engine that runs in Google Chrome and other Chromium-based web browsers
  - It was designed with performance in mind and is responsible for compiling JavaScript directly to native machine code that your computer can execute.
  - Node programs are NOT executed in a browser. Ryan Dahl took the V8 engine and enhanced it with various features, such as a file system API, an HTTP library, and a number of operating system–related utility methods
  - This means that Node.js is a program we can use to execute JavaScript on our computers.

---

- ### Helpful Terminal Commands
  - $ `node file_name.js` to execute the file
  - $ `node -v` will show you the version of Node installed on your local machine.
  - $ `npm -v` to check which version of Node Package Manager is installed 
  - $ `npm init -y` will simply generate an empty npm project and auto-populate a package.json file in the same folder without going through an interactive process. The -y stands for yes.

---

- ### Node Package Manager (npm)
  - In addition to being the package manager for JavaScript, npm is also the world’s largest software registry. 
  - `node_modules` is where npm saves packages and any libraries that those packages depend on. The `node_modules` folder shouldn’t be checked in to version control, and can, in fact, be re-created at any time by running npm install ($ `npm i`) from within the project’s root.
  - inside the `package.json` file is all of the project's dependencies which will allow any developer anywhere to clone your project and use npm to install whatever packages it needs to run.

---

- ### Install Node
  - [Official Node Download Page](https://nodejs.org/en/download/)
  - [Install Multiple Versions of Node.js using nvm.](https://www.sitepoint.com/quick-tip-multiple-versions-node-nvm/)
  - $ `node -v` will show you the version of Node installed on your local machine.

---

## 📚 Resources Used in "Node.js"
- [Node.js](https://www.sitepoint.com/an-introduction-to-node-js/)