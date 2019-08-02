### Register onTouched

```typescript
interface ControlValueAccessor {
  writeValue(obj: any): void
  registerOnChange(fn: any): void
  registerOnTouched(fn: any): void //<----
  setDisabledState(isDisabled: boolean)?: void
}
```

Registers a callback function is called by the forms
<br />API on initialization to update the form model on blur.