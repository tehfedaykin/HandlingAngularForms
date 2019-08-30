### Three

Update changed fields validity.

```typescript
onChanges() {
  const subCategoryControl = this.recipeForm.get('subcategory');

  this.recipeForm.get('category').valueChanges.subscribe(val => {
    if (val) {
      subCategoryControl.setValidators(Validators.required);
      subCategoryControl.updateValueAndValidity();
    }
    else {
      subCategoryControl.setValidators(null);
      subCategoryControl.updateValueAndValidity();
    }
  });
}
```