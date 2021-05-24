## List from array

> users-list.component.ts

```ts
class UsersListComponent {
  users: User[] = [];
}
```

> users-list.component.html

```html
<li *ngFor="let user of users">
  <p>Name: {{ user.name }}</p>
  <p>Age: {{ user.age }}</p>
</li>
```
