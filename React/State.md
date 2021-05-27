# State in React

State is needed whenever a component wants to **keep track** of something that is going to change dinamically **over time**. Any change to a component's state will cause React to **render the component again**.

```js
const App = () => {
  const [counter, setCounter] = useState(0);

  const handleClick = () => {
    setCounter((current) => current + 1);
  };

  return <button onClick={handleClick}>{counter}</button>;
};
```
