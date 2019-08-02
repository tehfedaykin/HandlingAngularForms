### Testing Rating Disabling

```typescript
it('should not call touch or change events when disabled', () => {
  testHostComponent.rating.patchValue(3);
  testHostComponent.rating.disable();
  hostFixture.detectChanges();
  const compiled = hostFixture.debugElement.nativeElement;
  let star1 = compiled.querySelector('gr-star-rater .stars .star');
  star1.dispatchEvent(new Event('click'));
  hostFixture.detectChanges();
  expect(testHostComponent.rating.value).toBe(3);
});
```

We care that component implements "disabled" functionality correctly.