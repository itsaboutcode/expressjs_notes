# What's [dotenv](https://www.npmjs.com/package/dotenv) package

Dotenv is a module that loads `environment` variables from a `.env` file into `process.env`. Please follow the steps I've included below to use this package.

### 01 - Install the package

`npm install dotenv`

### 02 - Usage

Create a `.env` file in the `root` of your project:

### 03 - Populate the key/value pair in the `.env` file


```
S3_BUCKET="YOURS3BUCKET"
SECRET_KEY="YOURSECRETKEYGOESHERE"
```

### 04 - Import the library in your project

Do the following `as soon as` possible in your application (normally in your project starter file)

`require('dotenv').config()`

#### ES6 syntax

`import 'dotenv/config'`

### 05 - Use the env variables

`console.log(process.env.S3_BUCKET)`

