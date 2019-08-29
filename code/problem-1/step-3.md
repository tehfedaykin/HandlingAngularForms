### Three

Update changed fields validity.

```typescript
onChanges() {
  this.recipeForm.get('category').valueChanges.subscribe(val => {
    const subCategoryControl = this.recipeForm.get('subcategory');
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