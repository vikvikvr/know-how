# Express controller

## Basic controller

```js
controllers.post = function (req, res) {
  // read url parameter
  const { id } = req.params;
  // get request body (use express.json() middleware!)
  const data = req.body;
  // set response status code
  res.status(201);
  // send response body
  res.send({ bar: 'foo' });
};
```

## Async controller

```js
controllers.get = async function (req, res) {
  try {
    const users = await User.find();
    res.send(users);
  } catch (error) {
    // shorthand to send status code without a body
    res.sendStatus(500);
  }
};
```
