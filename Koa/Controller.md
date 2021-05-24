```js
exports.addUser = async function (ctx) {
  // set response status code
  ctx.status = 201;
  // set response body
  ctx.body = { bar: 'foo' };
  // read url parameter
  const userId = ctx.params.id;
  // get request body (use koa-bodyparser middleware!)
  const userData = ctx.request.body;
};
```
