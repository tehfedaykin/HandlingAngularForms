```typescript
import { Component, OnInit } from '@angular/core';
import { FormControl, FormGroup, FormArray, Validators } from '@angular/forms';

let emailRegex = "^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+.[a-zA-Z0-9-.]+$";

@Component({
  selector: 'app-formarray',
  template: `
   <form [formGroup]="usersForm" (ngSubmit)="onSubmit()">
    <ng-container *ngFor="let userFG of usersForm.controls; let i = index">
      <div [formGroup]="userFG">
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
      </div>
    </ng-container>
    <button type="submit">console log form value</button>
  </form>
  `
})
export class FormarrayComponent implements OnInit {
  public usersForm = new FormArray([
    new FormGroup({
      firstName: new FormControl('user 1', {validators: Validators.required}),
      lastName: new FormControl('', {validators: Validators.required}),
      email: new FormControl('', {validators: Validators.pattern(emailRegex)})
    }),
    new FormGroup({
      firstName: new FormControl('user 2', {validators: Validators.required}),
      lastName: new FormControl('', {validators: Validators.required}),
      email: new FormControl('', {validators: Validators.pattern(emailRegex)})
    })
  ]);

  constructor() { }

  ngOnInit() { }

  onSubmit() {
    console.log(this.usersForm.value);
  }
}
```