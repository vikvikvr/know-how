## Use router instead of components

> app.component.html

```html
<nav>shared navbar</nav>
<router-outlet></router-outlet>
<footer>shared footer</footer>
```

## Add routes to components

> app-routing.module.ts

```ts
import { UsersListComponent } from './users-list/users-list.component';

const routes: Routes = [{ path: '', component: UsersListComponent }];
```

## Add link to route

> user-item.component.html

```html
<a routerLink="user/{{user._id}}">details</a>
```

## Change route programmatically

> dashboard.component.ts

```ts
// 1. import dependency
import { Router } from '@angular/router';

// 2. inject dependency
constructor(private router: Router) { }

handleClick () {
  // 3. use router method
  this.router.navigate(['users/add']
}
```

## Access route parameters

> user-details.component.ts

```ts
// import dependency
import { ActivatedRoute } from '@angular/router';

// inject dependency
constructor(private route: ActivatedRoute) { }

// given the route 'user/:id'
someMethod(): void {
  // read route parameter
  const idString = this.route.snapshot.paramMap.get('id');
  if (idString !== null) {
    const id = parseInt(idString);
  }
}
```
