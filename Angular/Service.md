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
