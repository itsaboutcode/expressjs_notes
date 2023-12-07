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
npm i express mongoose dotenv body-parser cors helmet morgan
npm i -D nodemon
```

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

# Reference

- https://expressjs.com/
