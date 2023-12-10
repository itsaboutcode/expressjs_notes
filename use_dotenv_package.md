# What is the [dotenv](https://www.npmjs.com/package/dotenv) package?

[dotenv](https://www.npmjs.com/package/dotenv) is a module designed to load environment variables from a `.env` file into the `process.env` object. Follow the outlined steps below to seamlessly integrate this package into your project.


### Step 01 - Install the package

`npm install dotenv`

### Step 02 - Usage

Create a `.env` file in the `root` of your project:

### Step 03 - Populate the Key/Value Pairs in the .env File


```
S3_BUCKET="YOURS3BUCKET"
SECRET_KEY="YOURSECRETKEYGOESHERE"
```

### Step 04 - Import the Library into Your Project

Include the following code as early as possible in your application, typically in your project's main file.

`require('dotenv').config()`

#### ES6 syntax

`import 'dotenv/config'`

### Step 05 - Utilize the Environment Variables

Access and use the defined environment variables in your code.

`console.log(process.env.S3_BUCKET)`

