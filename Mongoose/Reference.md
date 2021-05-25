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

In the mongoDB world, this would correspond to the following **collections**:

```json
{
  "messages": [
    {
      "content": "something clever",
      "author": "USER_6cee1e8d8f2a86c34b01c230a50",
      "_id": "MSG_57a02e621dc1d9ab670e79217455"
    },
    {
      "content": "something smart",
      "author": "USER_bf9682a54af5ab9364dda5eb69b",
      "_id": "MSG_a0fd03633ebcabf4a5e1ef280188"
    }
  ],
  "users":[
    {
      "name": "Adam",
      "_id": "USER_6cee1e8d8f2a86c34b01c230a50"
    },
    {
      "name": "Bob",
      "_id": "USER_bf9682a54af5ab9364dda5eb69b"
    }
  ]}
}
```

When making a "message" query, we need to tell mongoose that we want to **populate the author field** with the corresponding user object instead:

```js
Message.find({}).populate('author').exec();
```
