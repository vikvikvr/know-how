## Using state

The state must have a default value. Any change to it must be done using the setState() method.

```js
class App extends React.Component {
  state = { counter: 0 };

  handleClick() {
    this.setState({ counter: this.state.counter + 1 });
  }
}
```

## Inner workings of setState

Given a proposed stateChange, it will check if the result of merging the change with the current state will result in a different overall state. If so, it will trigger a new render.

```js

class React.Component {

  setState(stateChange) {
    const newState = Object.assign({}, this.state, stateChange);
    if (!deepEqual(newState, this.state)) {
      this.state = newState;
      this.render();
    }
  }
}
```
