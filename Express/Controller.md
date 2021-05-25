# Express controller

A controller only deals with the **network layer**. Given some info about the requests coming in, **waits for the model** to give it some data and sends back a response to the client based on the result.

## Basic controller

It is **just a function** that given two objects, it will send back a response to the client using a method on the second one.

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

Needed if we want to leverage the nice **await** syntax when using promises.

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
