### In form markup

```html
<form [formGroup]="myForm">
  <div class="form-group">
    <label for="name">Name</label>
    <my-sweet-component class="form-control" formControlName="name"></my-sweet-component>
  </div>
</form>
```

Same as ...

```html
<form [formGroup]="myForm">
  <div class="form-group">
    <label for="name">Name</label>
    <my-sweet-component class="form-control" [formControl]="myForm.controls.name"><my-sweet-component>
  </div>
</form>
```