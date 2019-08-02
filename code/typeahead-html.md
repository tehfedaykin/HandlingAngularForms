### Typeahead markup

```html
<ng-template #template let-model="item" >
  {{model.name}}
</ng-template>
<input 
  class="form-control" [(ngModel)]="selected" [typeahead]="data"
  typeaheadOptionField="name" [typeaheadItemTemplate]="template" [typeaheadMinLength]="0" 
   (typeaheadOnSelect)="onSelect($event)" (blur)="onBlur($event)" >
```

(using <a href="https://valor-software.com/ngx-bootstrap/#/typeahead" target="_blank">ngx-bootstrap</a> typeahead)