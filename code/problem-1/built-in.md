### Built-in Validation

```typescript
const control = new FormControl('some value', {
  validators: Validators.required
});
```

<p>We have several built-in validators at our disposal:</p>
<p class="small">min(), max(), required(), requiredTrue(), email(), minLength(),
<br />maxLength(), pattern(), nullValidator(), compose(),
composeAsync()</p>