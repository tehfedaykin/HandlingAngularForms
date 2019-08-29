```typescript
import { Component, OnInit } from '@angular/core';
import { FormControl } from '@angular/forms'

@Component({
  selector: 'app-basic',
  template: `<input type="text" [formControl]="name">`
})
export class BasicComponent implements OnInit {
  public name = new FormControl('your name here');

  constructor() { }
  ngOnInit() { }
}
```