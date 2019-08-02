Our Reactive Form

```typescript
this.galaxyForm = new FormGroup({
  galaxy: new FormControl({value: null, disabled: false}, [Validators.required]),
  rating: new FormControl({value: null, disabled: true}, [Validators.required]),
  name: new FormControl({value: null, disabled: false}, [Validators.required])
})
```