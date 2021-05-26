# Async code in React

## Making an API request

You want to store **external data you get after a delay** in the component's **state**. This way React will know it needs to **trigger a new render** of the component whenever the data is finally available.

```js
import { useState, useEffect } from 'react';
import { api } from './api';

const App = () => {
  const [movies, setMovies] = useState([]);

  useEffect(() => {
    // this code will only run once on mount
    api.getMovies().then((fetchedMovies) => {
      // updating the state will cause a re-render
      setMovies(fetchedMovies);
    });
  }, []);

  return <div>Found {movies.length} movies</div>;
};
```
