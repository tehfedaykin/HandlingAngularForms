## Scenario

```html
<form [formGroup]="recipeForm" (ngSubmit)="onSubmit()">
  <div class="form-group">
    <label for="category">Category</label>
    <ng-container *ngFor="let category of categories">
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="radio" 
        [value]="category.id" formControlName="category">
        <label class="form-check-label">{{category.name}}</label>
      </div>
    </ng-container>
  </div>
  <div class="form-group" *ngIf="recipeForm.controls.category.value">
    <label for="category">Subcategory</label>
    <my-checkboxes formControlName="subcategory" [data]="subcategories">
    </my-checkboxes>
  </div>
  <button type="submit" class="btn btn-primary">Save Recipe</button>
</form>
```