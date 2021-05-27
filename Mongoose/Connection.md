## Connect to the database

In the models folder we create a separate file that **only cares about creating a connection** to the mongo database 🍃.

```js
const mongoose = require('mongoose');

const url = 'mongodb://localhost:27017/playground';

mongoose.connect(url, {
  useNewUrlParser: true,
  useUnifiedTopology: true
});

module.exports = mongoose;
```

Inside the models we will always use the export from this file, instead of the one coming from the library. This allows us to reference the same connection each time, without the need to create new ones (which would cause a memory leak).
