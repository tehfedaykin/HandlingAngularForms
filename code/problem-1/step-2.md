### Two

Get fields control and use setValidators method.

```typescript
onChanges() {
  const subCategoryControl = this.recipeForm.get('subcategory');
  
  this.recipeForm.get('category').valueChanges.subscribe(val => {
    if (val) {
      subCategoryControl.setValidators(Validators.required);
    }
    else {
      subCategoryControl.setValidators(null);
    }
  });
}
```