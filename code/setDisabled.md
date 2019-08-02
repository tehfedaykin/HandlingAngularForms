### Set Disabled State(optional)

```typescript
interface ControlValueAccessor {
  writeValue(obj: any): void
  registerOnChange(fn: any): void
  registerOnTouched(fn: any): void 
  setDisabledState(isDisabled: boolean)?: void //<----
}
```

Function that is called by the forms API when the control status changes to or from 'DISABLED'. This will be called when the FormControl is instantiated IF the disabled key is present AND when .enable() or .disable() is called.
