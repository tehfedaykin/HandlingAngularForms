### In form markup

```html
<form [formGroup]="myForm">
  <div class="form-group">
    <label for="rating">Rating</label>
    <my-sweet-component class="form-control" formControlName="rating"></my-sweet-component>
  </div>
</form>
```

Same as ...

```html
<form [formGroup]="myForm">
  <div class="form-group">
    <label for="rating">Rating</label>
    <my-sweet-component class="form-control" [formControl]="myForm.controls.rating"><my-sweet-component>
  </div>
</form>
```