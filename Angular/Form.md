## Add dependency

> app.module.ts

```ts
import { ReactiveFormsModule } from '@angular/forms';

{
  imports: [ReactiveFormsModule];
}
```

## Build the template

> user-form.component.html

```html
<form [formGroup]="userForm" (ngSubmit)="onSubmit()">
  <label>
    Name:
    <input type="text" formControlName="name" />
  </label>
  <label>
    Age:
    <input type="number" formControlName="age" />
  </label>
  <input type="submit" value="save" />
</form>
```

## Build the component

> user-form.component.ts

```ts
// 3. build the component
import { FormControl, FormGroup } from '@angular/forms';

export class AddUserFormComponent implements OnInit {
  // define form shape
  userForm = new FormGroup({
    name: new FormControl(''),
    age: new FormControl('')
  });

  onSubmit(): void {
    // get form data
    console.log(this.userForm.value);
    // update parts of the form
    this.userForm.patchValue({ name: 'Anne' });
    // update the whole form
    this.userForm.setValue({ age: 99, name: 'Bob' });
  }
}
```

## With form builder and validation

> user-form.component.ts

```ts
import { FormBuilder, Validators } from '@angular/forms';

export class AddUserFormComponent {
  userForm = this.fb.group({
    name: ['', Validators.required],
    age: [26, [Validators.required, Validators.min(18)]]
  });
  constructor(private fb: FormBuilder) {}
}
```

> user-form.component.html

```html
<form [formGroup]="userForm">
  ...
  <button (click)="onSubmit()" [disabled]="userForm.invalid">save</button>
</form>
```
