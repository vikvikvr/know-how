## Use service inside component

> dashboard.component.ts

```ts
import { ApiClientService } from '../api-client.service';

// inject service
constructor(private api: ApiClientService) { }

ngOnInit(): void {
  // use service methods
  this.api.getDiscoverMovies();
}
```

## Parsing data from api call

Pipe and map allow you to modify the object wrapped by the observable before emitting the value.

> api-client.service.ts

```ts
class ApiClientService {
  fetchMovies(): Observable<Movie[]> {
    return this.http
      .get('some-url')
      .pipe(
        map((movies: object[]) => movies.map((movie) => Movie.parse(movie)))
      );
  }
}
```
