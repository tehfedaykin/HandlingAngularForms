### Solution #1

```typescript
@Component({
  selector: 'meh-component',
  template: `<input (change)="mehChange($event)" type="text" />`,
})
export class MehComponent implements OnInit {
  @Output() mehValueChange = new EventEmitter();
  mehChange($event) {
    this.mehValueChange.emit($event.currentTarget.value);
  }
}
```