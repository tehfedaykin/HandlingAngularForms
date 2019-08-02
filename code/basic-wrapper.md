### Basic CVA implementation

```typescript 
export class MySweetComponent implements ControlValueAccessor {
  _value: any;
  onChange;
  onTouched;
  writeValue(val) { this._value = val;}
  registerOnChange( fn : any ) : void { this.onChange = fn; }
  registerOnTouched( fn : any ) : void { this.onTouched = fn; }
  
  sweetChange($event) {
    this._value = $event.currentTarget.value;
    this.onTouched();
    this.onChange($event.currentTarget.value);
  }
}
```