# Props in React

## Passing data down

**Props** are how a parent passes data down to a child. They **can be of any type** (primitive values, objects, functions).

```js
const Parent = () => {
  return <Child name="Bob" age={32} />;
};

// <Parent> ---{name,age}--> <Child>

const Child = (props) => {
  return (
    <div>
      <h1>Name: {props.name}</h1>
      <h2>Age: {props.age}</h2>
    </div>
  );
};
```

## Passing data up

A child can notify its parent about something by using **callbacks**. The parent would pass to the child a **reference to a function**, that in turn the child can call later on. To pass data back to the parent, the child must provide the callback with some argument(s).

```js
const Parent = () => {
  const handleClick = (text) => {
    console.log('child says', text);
  };
  return <Child onClick={handleClick} />;
};

// <Parent> ---{onClick}--> <Child>

const Child = (props) => {
  return <button onClick={() => props.onClick('Hello')}>child</button>;
};

// <Parent> <--onClick('hello')-- <Child>
```
