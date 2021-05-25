## Create a model

A model is a collection of rules and methods that allow us to interact with the database without ever worrying about its nature.

We abstract away the infrastructure-layer and we only concern with the **data-layer** instead.

```js
// connection we created in a separate file
const mongoose = require('./database');

// Schema -> describes the shape of our data
const userSchema = new mongoose.Schema({
  name: String,
  age: Number
});

// Model -> provides db methods enforcing schema rules
const User = mongoose.model('User', userSchema);

module.exports = User;
```
