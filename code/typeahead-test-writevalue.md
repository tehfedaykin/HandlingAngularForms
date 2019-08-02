### Testing writeValue

```typescript
// public testData = [{id: 1, name: 'foo'},{id: 2, name: 'bar'}];
it('should select dropdown based on formControl value', () => {
  testHostComponent.galaxy.patchValue(1);
  hostFixture.detectChanges();
  expect(testHostComponent.typeaheadComponent.selected).toEqual('foo');
});
```

We care that the ui selects the marks the appropriate dropdown as selected when writeValue is called.
