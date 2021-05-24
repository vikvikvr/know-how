## Endpoints for CRUD operations

```js
const Router = require('koa-router');
const user = require('./user.controller');

const router = new Router();

// endpoints
router.get('/users', user.getAllUsers);
router.post('/user', user.addUser);
router.put('/user/:id', user.updateUser);
router.delete('/user/:id', user.deleteUser);

module.exports = router;
```
