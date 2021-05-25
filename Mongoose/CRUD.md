## CRUD operations

We use model methods **inside the relative controller**.

```js
// inside user.controller.js

const User = require('./User.model');

// CREATE
await User.create(userData);
// READ
await User.find({});
await User.findById(userId);
// UPDATE
await User.updateOne({ _id: userId }, userData);
// DELETE
await User.deleteOne({ _id: userId });
```
