# How to use [i18n](https://www.npmjs.com/package/i18n) package

In scenarios where it's necessary to communicate messages in a language that aligns with the user's preferred language, the `i18n` package becomes essential. Consider a typical `REST` API scenario where the front-end application supports multiple languages. In such cases, it's crucial to convey success and error messages in the user's native language to enhance the user experience.

## How to use it

Follow the steps below to use it as express.js `middleware`

### Step 01 - Install the package

`npm install i18n`

### Step 02: Configure i18n

Create a folder for your language files `(e.g., locales)` and define language-specific error messages in separate JSON files `(e.g., en.json, es.json)`. For example:

`locales/es.json:`

```
{
  "errorMessages": {
    "notFound": "Resource not found",
    "internalServerError": "Internal server error"
    // Add more error messages as needed
  }
}

```

### Step 03: Create languageMiddleware.js

```
// languageMiddleware.js
const i18n = require('i18n');

const languageMiddleware = (req, res, next) => {
  const requestedLanguage = req.get('Accept-Language');
  if (requestedLanguage && i18n.getLocales().includes(requestedLanguage)) {
    req.setLocale(requestedLanguage);
  }
  next();
};

module.exports = languageMiddleware;

```


### Step 04: Configure i18n in your Express.js app:

```
const express = require('express');
const i18n = require('i18n');
const path = require('path');
const languageMiddleware = require('./languageMiddleware');

const app = express();

// Configure i18n
i18n.configure({
  locales: ['en', 'es'],
  directory: path.join(__dirname, 'locales'),
  defaultLocale: 'en',
  cookie: 'lang',
});

// Set i18n in the app
app.use(i18n.init);

// Use the language middleware
app.use(languageMiddleware);

// ... other middleware and routes ...

// Example of using language-specific error messages
app.use((req, res, next) => {
  const err = new Error('Not Found');
  err.status = 404;
  next(err);
});


// Start the server
const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`);
});

app.get('/hello_world_error', (req, res) => {

  res.status(200).json({error: res.__('errorMessages.internalServerError') })

})

```


