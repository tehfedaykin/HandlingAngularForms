### Testing Rating Change Event

```typescript
it('should call change with rating value when star selected', () => {
  const compiled = hostFixture.debugElement.nativeElement;
  let star3 = compiled.querySelectorAll('gr-star-rater .stars .star')[2];
  star3.dispatchEvent(new Event('click'));
  hostFixture.detectChanges();
  expect(testHostComponent.rating.value).toBe(3);
});
```

We care that the formControl is being notified of the change when a star is clicked.