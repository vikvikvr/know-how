```sh
ng add @fortawesome/angular-fontawesome
```

> app.module.ts

```ts
import { FontAwesomeModule } from '@fortawesome/angular-fontawesome';

@NgModule({
  declarations: [
    FontAwesomeModule,
  ]
})
```

> app.component.ts

```ts
import { faBars } from '@fortawesome/free-solid-svg-icons';

export class AppComponent {
  faBars = faBars;
}
```

> app.component.html

```html
<fa-icon [icon]="faBars" size="2x"></fa-icon>
```
