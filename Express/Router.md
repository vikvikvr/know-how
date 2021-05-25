# Express Router

## Minimal setup

It should just be a map between endpoints and controllers.

```js
const { Router } = require('express');
const controllers = require('./controllers');

const router = Router();

router.get('/endpoint', controllers.get);
router.post('/endpoint', controllers.post);
router.put('/endpoint', controllers.put);
router.delete('/endpoint', controllers.delete);

module.exports = router;
```

## Dynamic routes

```js
// matches /endpoint/1234/banana
router.get('/endpoint/:id/:name', controllers.get);

// access params inside controller
controllers.get = function (req, res) {
  const { id, name } = req.params;
}
```
