# Express Server

## Minimal setup

This is not handling any requests yet!

```js
const express = require('express');

const app = express();

const PORT = 3000;

app.listen(PORT, () => {
  console.log('Running on port', PORT);
});
```

## Dealing with CORS

Needed when receiving requests from a **different ip / port**. 🔀
For instance:

- express-server: `localhost:3000`
- angular-client: `localhost:4200`

```js
const cors = require('cors');

app.use(cors());
```

💡 With **typescript** `npm i -D @types/cors`.

## Serving static files

Part of the SSR (Server Side Rendering). Our server delivers everything to the client (**html, css, js, assets**); 🗃 it does not only send JSON data back.

```js
app.use(express.static('path-to-static-folder'));
```

## Parsing JSON request body

When a body comes in within a request, it is actually a buffer of raw text-like data. To abstract away from this we simply use a **middleware** that takes care of that. 🌟

```js
app.use(express.json());
```

## Using a router

Always create the router in a **separate file**.

```js
const router = require('./router.js');

app.use(router);
```
