# Handle clicks in React

## Within the component itself

```js
const MovieItem = ({ title }) => {
  // It's a closure, relies on the "title" prop
  const handleClick = () => {
    console.log('clicked movie', title);
  };

  return <div onClick={handleClick}>Title: {title}</div>;
};
```

## In the parent component

```js
// dumb component: uses props to show stuff on screen
// and to notify the parent about a click

const MovieItem = ({ title, clickHandler }) => {
  return <div onClick={() => clickHandler(title)}>{title}</div>;
};

// smart component: creates the data to pass to its children
// and handles the logic related to clicks

const MoviesList = () => {
  const handleClick = (movieTitle) => {
    console.log('clicked movie', movieTitle);
  };

  const movieTitles = ['Harry Potter', 'Forest Gump'];

  return (
    <div>
      {movieTitles.map((title) => (
        <MovieItem title={title} onClick={handleClick} />
      ))}
    </div>
  );
};
```
