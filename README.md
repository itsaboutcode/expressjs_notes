# [ExpressJS](https://expressjs.com/)


These notes will teach us how to create Application **programming interfaces (APIs)** in a standard called **representational state transfer (REST**).

For the DB, we will use MongoDB.

### Creating ExpressJS Project

#### 1. Install [NodeJS](https://nodejs.org/en/) and confirm that it's installed

```
node -v
npm -v
```

#### 2. Create project Directory

```
mkdir sample_exressjs_rest_api_project

cd sample_exressjs_rest_api_project

```

#### 3. Initialize new NodeJS Project

```
npm init -y
```

#### 4. Install ExpressJS and other dependencies

```
npm i express mongoose dotenv body-parser cors helmet morgan dotenv
npm i -D nodemon
mpm i mongodb-memory-server # if you want to do some mocking
npm i express-jwt jwks-rsa
```

- `body-parser:` You will use this dependency to convert the body of incoming requests into JavaScript objects.

- `cors:` You will use this dependency to configure Express to add headers stating that your API accepts requests coming from other origins. This is known as Cross-Origin Resource Sharing (CORS).

- `express:` This is the Express library itself.

- `helmet:` This library helps to secure Express APIs by defining various HTTP headers.

- `morgan:` This library adds some logging capabilities to your Express API.

- `nodemon:` Nodemon to restart our server every time we save our file.

- `dotenv:` Dotenv to manage a .env file.

- `mongoose:` Mongoose for managing data in MongoDB using various queries

- `mongodb-memory-server:` Local in-memory mongoDB instance which will delete everything whenever you restart your server

- `express-jwt:` A middleware that validates JSON Web Tokens (JWTs) and sets the req.user with its attributes.

- `jwks-rsa:` A library to retrieve RSA public keys from a JWKS (JSON Web Key Set)

#### 5. Create an index.js file and write the following Hello World program

```
const express = require('express');

const PORT = process.env.PORT || 3000;

const app = express ();
app.use(express.json());


app.listen(PORT, () => {
  console.log("Server Listening on PORT:", PORT);
});

```

#### 6. Run the Server

```
node index.js
```

**Output**

```
Server Listening on PORT: 3000
```

#### 7. Creating the first REST End Point

```
app.get("/hello", (req, res) => {

  res.send("Hello World");
});
```

#### 8. Restarting Server Automatically

In the `package.json` file, add a script that says the following:

"scripts": {
    "start": "nodemon index.js"
},

Run the server with following command

```
npm start
```

**Sample Output**

```
> nodemon index.js

[nodemon] 3.0.2
[nodemon] to restart at any time, enter `rs`
[nodemon] watching path(s): *.*
[nodemon] watching extensions: js,mjs,cjs,json
[nodemon] starting `node index.js`
Server Listening on PORT: 3000
```


### JS Concepts

1. const
2. let
3. async

# Reference

- https://expressjs.com/
