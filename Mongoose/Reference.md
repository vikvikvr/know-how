
## Reference other collections

Reference other collections through an ObjectId.

```js
const { Schema } = require('mongoose');
const { Types } = Schema;

const messageSchema = new Schema({
  content: String,
  author: { type: Types.ObjectId, ref: 'User' }
});
```
