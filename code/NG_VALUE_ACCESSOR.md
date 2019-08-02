```typescript
import { NG_VALUE_ACCESSOR } from '@angular/forms';
@Component({
  selector: 'my-sweet-component',
  template: `<input (change)="sweetChange($event)" type="text" />`,
  providers: [{
    provide: NG_VALUE_ACCESSOR,
    useExisting: forwardRef(() => MySweetComponent),
    multi: true
  }]
})
export class MySweetComponent {
}
```

The NG_VALUE_ACCESSOR is used to register the component as a provider for the ControlValueAccessor, and because this will register the component early we'll need to use forwardRef to refer to it.