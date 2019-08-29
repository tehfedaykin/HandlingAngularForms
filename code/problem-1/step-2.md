### Two

Get fields control and use setValidators method.

```typescript
onChanges() {
  this.recipeForm.get('category').valueChanges.subscribe(val => {
    const subCategoryControl = this.recipeForm.get('subcategory');
    if (val) {
      subCategoryControl.setValidators(Validators.required);
    }
    else {
      subCategoryControl.setValidators(null);
    }
  });
}
```