```typescript
import { FormBuilder, FormGroup, Validators } from '@angular/forms';
...
@Component({
  selector: 'app-formbuilder',
  template: `...`
})
export class FormbuilderComponent implements OnInit {
  public usersForm: FormGroup;

  constructor(private fb: FormBuilder) { }

  ngOnInit() {
    this.usersForm = this.fb.group({
      date: this.fb.control(new Date()),
      users: this.fb.array([
        this.fb.group({
          firstName: [{value: 'user 1', disabled: false}, Validators.required],
          lastName: [{value: '', disabled: false}, Validators.required],
          email: [{value: '', disabled: false}, Validators.pattern(emailRegex)]
        }),
        this.fb.group({
          firstName: [{value: 'user 2', disabled: false}, Validators.required],
          lastName: [{value: '', disabled: false}, Validators.required],
          email: [{value: '', disabled: false},  Validators.pattern(emailRegex)]
        })
      ])
    })
  }

  onSubmit() {
    console.log(this.usersForm.value);
  }
}
```