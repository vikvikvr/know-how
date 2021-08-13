# Authentication with Express

## Using Passport.js

### 1. Create strategies

> strategies.js

```js
const GoogleStrategy = require('passport-google-oauth').OAuth2Strategy;

const google = new GoogleStrategy(
  {
    clientID: process.env.GOOGLE_CLIENT_ID,
    clientSecret: process.env.GOOGLE_CLIENT_SECRET,
    callbackURL: '/login/google/callback'
  },
  function (accessToken, refreshToken, profile, done) {
    return done(null, profile);
  }
);

module.exports = { google };
```

### 2. Setup passport instance

> passport.js

```js
const passport = require('passport');

// serialization

passport.serializeUser((user, done) => {
  done(null, user.id);
});

passport.deserializeUser((id, done) => {
  let user = users.find((u) => u.id === id);
  done(null, user || false);
});

// register strategies

passport.use(googleStrategy);
passport.use(facebookStrategy);
passport.use(gitHubStrategy);

module.exports = middlewares;
```

### 3. Start server

```js
const express = require('express');
const dotenv = require('dotenv');
const appRouter = require('./routers/app-router');
// it's the local one, not the one from node_modules
const passport = require('./passport');
const loginRouter = require('./routers/login-router');
const cookieSession = require('cookie-session');

dotenv.config();

function setupMiddlewares(app) {
  const formMiddleware = express.urlencoded({ extended: true });
  const cookieMiddleware = cookieSession({
    maxAge: 24 * 60 * 60 * 1000,
    keys: [process.env.COOKIE_KEY]
  });

  app.use(cookieMiddleware);
  app.use(formMiddleware);
  app.use(passport.initialize());
  app.use(passport.session());
  app.use(loginRouter);
  app.use(appRouter);
}

const app = express();

app.set('view engine', 'pug');
app.set('views', 'src/views');

setupMiddlewares(app);

const port = process.env.PORT || 3000;

app.listen(port, () => {
  console.log('server started on port ', port);
});
```
