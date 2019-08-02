### writeValue

```typescript
interface ControlValueAccessor {
  writeValue(obj: any): void //<----
  registerOnChange(fn: any): void
  registerOnTouched(fn: any): void
  setDisabledState(isDisabled: boolean)?: void
}
```

Writes a new value to the element. This will be called when the FormControl is instantiated AND when patchValue or setValue is called.