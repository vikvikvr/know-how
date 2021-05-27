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

Get new document after an update query

```js
const filter = { _id: ctx.params.id };
const query = { $inc: { score: 1 } };
const options = { new: true };
const newTopic = await Topic.findOneAndUpdate(filter, query, options);
```
