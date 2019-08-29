 ### Create Add & Remove Methods
 
```typescript
public addIngredient() {
  const ingredientsFormArray = <FormArray>this.recipeForm.controls['ingredients'];
  const ingredientFormGroup = new FormGroup({
    name: new FormControl(null, [Validators.required]),
    amount: new FormControl(null, [Validators.required])
  });
  ingredientsFormArray.insert(ingredientsFormArray.length, ingredientFormGroup);
}

public removeIngredient(i) {
  const ingredientsFormArray = <FormArray>this.recipeForm.controls['ingredients'];
  ingredientsFormArray.removeAt(i);
}
```