## Connect to the database

Create a connection to mongoDB with Mongoose. Inside the models, require this instead of the actual module.

```js
const mongoose = require('mongoose');

const url = 'mongodb://localhost:27017/playground';

const settings = {
  useNewUrlParser: true,
  useUnifiedTopology: true
};

mongoose.connect(url, settings);

module.exports = mongoose;
```
