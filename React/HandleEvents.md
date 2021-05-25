# Handle events in React

Html elements have native properties that accept callbacks as values.

## Handle Clicks

Bind handler to the `onClick=` property.

### Within the component itself

Just bind the handler to onClick;

```js
class MovieItem extends React.Component {
  handleClick() {
    console.log(this.props.title);
  }

  render() {
    return <div onClick={this.handleClick}>something</div>;
  }
}
```

### In the parent component

Pass a reference of the handler (parent's method) to the child, and call it inside the child when a click happens.

```js
class MovieItem extends React.Component {
  render() {
    return <div onClick={this.props.onClick}>something</div>;
  }
}

class MoviesList extends React.Component {
  handleClick(movie) {
    console.log(movie.title);
  }

  render() {
    const movies = [{ title: 'Harry Potter', title: 'Forest Gump' }];
    return (
      <div>
        {movies.map((movie) => (
          <MovieItem onClick={() => this.handleClick(movie)} />
        ))}
      </div>
    );
  }
}
```
