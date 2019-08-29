### Function Validation

```typescript
minValidator(c: FormControl) {
  return c.value.length > 2 ? null : {
    validAmount: {
      valid: false
    }
  };
}
const control = new FormControl('some value', {
  validators: [Validators.required, amountValidator]
});
```