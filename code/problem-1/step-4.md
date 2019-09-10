### Four

Add Custom Function Validation

```typescript
minValidator(c: FormControl) {
  return c.value.length > 2 ? null : {
    validAmount: {
      valid: false
    }
  };
}

onChanges() {
  this.recipeForm.get('category').valueChanges.subscribe(val => {
    const subCatCtrl = this.recipeForm.get('subcategory');
    if (val) {
      subCatCtrl.setValidators([Validators.required, this.minValidator]);
    }
    else {
      subCatCtrl.setValidators(null);
    }
  });
  subCatCtrl.updateValueAndValidity();
}
```