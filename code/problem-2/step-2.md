### Call methods in our markup

```html
<label for="ingredients">Ingredients</label>
<ng-container *ngFor="let ingredient of recipeForm.controls['ingredients'].controls; let i = index" >
  <div [formGroup]="ingredient" class="row">
    <div class="form-group col-sm">
      <label for="name">Name</label>
      <input class="form-control" formControlName="name" aria-describedby="name">
    </div>
    <div class="form-group col-sm">
      <label for="amount">Amount</label>
      <input class="form-control" formControlName="amount" aria-describedby="amount">
    </div>
    <div class="col-sm">
      <button class="btn btn-danger remove-ingredient" (click)="removeIngredient(i)">
        <fa-icon icon="times"></fa-icon>
      </button>
    </div>
  </div>
</ng-container>
<button type="button" class="btn btn-success" (click)="addIngredient()">Add ingredient</button>
```