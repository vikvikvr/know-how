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

## 🤷‍♂️ How setState kinda works

Given a **proposed stateChange**, it will check if the result of merging the change with the current state will result in a different overall state. If so, it will trigger a new render.

```js
class React.Component {

  setState(stateChange) {
    const newState = merge(stateChange, this.state);

    if (!deepEqual(newState, this.state)) {
      this.state = newState;
      this.render();
    }
  }
}
```
