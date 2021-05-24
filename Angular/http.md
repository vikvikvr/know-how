## Import dependency

> app.module.ts

```js
import { HttpClientModule } from '@angular/common/http';

{
  imports: [HttpClientModule],
}
```

## Use client in a service

> api-client.service.ts

```ts
import { HttpClient } from '@angular/common/http';

// inject dependency
constructor(private http: HttpClient) {}

getMovies(): Observable<Movie[]> {
  // make a request
  return this.http.get<Movie[]>('api-url');
}
```
