## Bootstrap

```js
// imports
const Koa = require('koa');
const router = require('./router');
const bodyParser = require('koa-bodyparser');
const cors = require('@koa/cors');

const app = new Koa();

// middlewares
app.use(cors());
app.use(bodyParser());
app.use(router.routes());

// bootsrap
app.listen(3000);
console.log('Server listening on port 3000');
```
