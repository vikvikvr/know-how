# Lifecycle hooks in React

## Component did mount

1️⃣ Executes **only once**, when the **component is created**.

```js
const Component = (props) => {
  useEffect(() => {
    console.log('component was created');
  }, []);
};
```

## Component did update

🔁 Executes **many times**, whenever any of the **dependencies change**.

```js
const Component = (props) => {
  useEffect(() => {
    console.log('props changed');
  }, [props]);
};
```

We might want to execute some actions only **when a specific 🔍 part of the state changes**.

```js
const Component = (props) => {
  const [counter, setCounter] = useState(0);
  const [clicks, setClicks] = useState(0);

  useEffect(() => {
    console.log('was clicked');
  }, [clicks]);

  useEffect(() => {
    console.log('counter changed');
  }, [counter]);
};
```

## Component will unmount

1️⃣ Executes **only once** when the component is removed from the app. The **function you return from useEffect** will be executed during **tear-down**.

```js
const Component = (props) => {
  useEffect(() => {
    return () => {
      console.log('component about to be destroyed');
    };
  }, []);
};
```
