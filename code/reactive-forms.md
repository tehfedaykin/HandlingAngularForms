
```html
<form>
  <label for="name">Name</form>
  <input class="form-control" [formControl]="name" ngModel>
</form>
```

```typescript
const name = new FormControl('Jennifer');
```