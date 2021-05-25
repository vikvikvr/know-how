## Fetch data

Any asyncronous request that we only need to perform once should be done inside the `componentDidMount` lifecycle method. After we get a result, we should update the state to trigger a new render.

```js
class App extends React.Component {
  componentDidMount() {
    getMovies().then((movies) => {
      this.setState({ movies });
    });
  }
}
```
