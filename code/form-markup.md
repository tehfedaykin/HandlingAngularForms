
### Form Markup

```html
<form [formGroup]="galaxyForm" (ngSubmit)="onSubmit()">
  <h1>Galaxy Rating App</h1>
  <div class="form-group">
    <label>Galaxy: <gr-typeahead [data]="galaxies"></gr-typeahead>
    </label>
  </div>
  <div class="form-group">
    <label>Rating: <gr-star-rater></gr-star-rater>
    </label>
  </div>
  <div class="form-group">
    <label>Name: <input type="text" class="form-control" />
    </label>
  </div>
...
```