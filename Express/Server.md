# Express Server

## Minimal setup

```js
const express = require('express');

const app = express();

const PORT = 3000;

app.listen(PORT, () => {
  console.log('Running on port', PORT);
});
```

## Dealing with CORS

Needed when receiving requests from a different ip address / port.

```js
const cors = require('cors');

app.use(cors());
```

## Serving static files

```js
app.use(express.static('path-to-static-folder'));
```

## Parsing JSON request body

```js
app.use(express.json());
```

## Using a router

Always create the router in a separate file.

```js
const router = require('./router.js');

app.use(router);
```
