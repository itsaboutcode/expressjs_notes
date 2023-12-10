# [ExpressJS](https://expressjs.com/)


These instructions guide us through the process of creating **Application Programming Interfaces (APIs)** using the **Representational State Transfer (REST)** standard. MongoDB will be employed as the database.

### Creating ExpressJS Project

#### Step 01 - Install [NodeJS](https://nodejs.org/en/) and Verify Installation

```
node -v
npm -v
```

#### Step 02 - Establish Project Directory

```
mkdir sample_exressjs_rest_api_project

cd sample_exressjs_rest_api_project

```

#### Step 03 - Initialize a New NodeJS Project


```
npm init -y
```

#### Step 04 - Install Dependencies

```
npm i express mongoose dotenv body-parser cors helmet morgan dotenv i18n
npm i -D nodemon
mpm i mongodb-memory-server # if you want to do some mocking
npm i express-jwt jwks-rsa
```

- [`body-parser:`](https://github.com/expressjs/body-parser) - Converts incoming request bodies into JavaScript objects.

- [`cors:`](https://github.com/expressjs/cors) - Configures Express to handle **Cross-Origin Resource Sharing (CORS)**.

- [`express:`](https://github.com/expressjs/express) - The Express Library.

- [`helmet:`](https://github.com/helmetjs/helmet) - Enhances Express API security through HTTP header definition.

- [`morgan:`](https://github.com/expressjs/morgan) - Adds logging capabilities to the Express API.

- `nodemon:` - Restarts the server on file save.

- `dotenv:` - Manages a .env file.

- `mongoose:` - Manages data in MongoDB.

- [`mongodb-memory-server:`](https://github.com/nodkz/mongodb-memory-server) - Local in-memory MongoDB instance.

- `express-jwt:` - Middleware for JSON Web Token (JWT) validation.

- `jwks-rsa:` - Retrieves RSA public keys from a JSON Web Key Set (JWKS).
  
#### Step 05 - Create an `index.js` File with a Hello World Program

```
const express = require('express');

const PORT = process.env.PORT || 3000;

const app = express ();
app.use(express.json());


app.listen(PORT, () => {
  console.log("Server Listening on PORT:", PORT);
});

```

#### Step 06 - Run the Server

```
node index.js
```

**Output**

```
Server Listening on PORT: 3000
```

#### Step 07 - Creating the First REST Endpoint

```
app.get("/hello", (req, res) => {

  res.send("Hello World");
});
```

#### Step 08 - Automatically Restart the Server

In `package.json`, add the following script:

"scripts": {
    "start": "nodemon index.js"
},

Run the server with:

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


- How to **Use [dotenv package](use_dotenv_package.md)**

- How to **Use [i18n package](use_i18n_package.md)**

### JavaScript Concepts

1. const
2. let
3. async

# Reference

- https://expressjs.com/
- https://12factor.net/
