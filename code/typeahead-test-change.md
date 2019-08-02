### Testing Change Event

```typescript
it('should send a change event with the new value when item is selected with new value', () => {
  testHostComponent.typeaheadComponent.selected = {
    id: 2,
    name: 'foo'
  }
  testHostComponent.typeaheadComponent.onSelect({item: {id: 3}});
  hostFixture.detectChanges();
  expect(testHostComponent.galaxy.value).toBe(3);
});
```

We care that the "galaxy" formControl is being notified of the change when an option is selected.
