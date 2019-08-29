```typescript
import { Component, OnInit } from '@angular/core';
import { FormControl, FormGroup, Validators } from '@angular/forms';

let emailRegex = "^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+.[a-zA-Z0-9-.]+$";

@Component({
  selector: 'app-formgroup',
  template: `
  <form [formGroup]="userForm" (ngSubmit)="onSubmit()">
    <label>
      First name:
      <input type="text" formControlName="firstName">
    </label>
    <label>
      Last name:
      <input type="text" formControlName="lastName">
    </label>
    <label>
      Email:
      <input type="text" formControlName="email">
    </label>
    <button [disabled]="!userForm.valid" type="submit">submit</button>
  </form>
  `
})
export class FormgroupComponent implements OnInit {
  public userForm = new FormGroup({
    firstName: new FormControl('', {validators: Validators.required}),
    lastName: new FormControl({value: 'last name here', disabled: true}, {}),
    email: new FormControl( '', {validators: Validators.pattern(emailRegex)})
  });

  constructor() { }

  ngOnInit() { }

  onSubmit() {
    console.log(this.userForm.value);
  }
}
```