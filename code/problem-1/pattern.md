### Pattern Validation

```typescript
const control = new FormControl('some value', {
	validators: Validators.pattern('[0-9]{5}')
});

const myDatePattern = "^\\d{2}\/\\d{2}\/\\d{4}$";
const otherControl = new FormControl('some value', {
  validators: Validators.pattern(myDatePattern)
});
```