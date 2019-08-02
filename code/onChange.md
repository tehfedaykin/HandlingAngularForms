### Register onChange

```typescript
interface ControlValueAccessor {
  writeValue(obj: any): void 
  registerOnChange(fn: any): void //<----
  registerOnTouched(fn: any): void
  setDisabledState(isDisabled: boolean)?: void
}
```

Registers a callback function that is called when
<br />the control's value changes in the UI.