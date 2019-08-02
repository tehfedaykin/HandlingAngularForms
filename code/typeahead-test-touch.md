### Testing Touch Event (& validation)

```typescript
  it('should set invalid class when field is required, has been touched, and has no value', () => {
    testHostComponent.galaxy.setValidators([Validators.required]);
    testHostComponent.typeaheadComponent.selected = null;
    const compiled = hostFixture.debugElement.nativeElement;
    let component = compiled.querySelector('gr-typeahead');
    expect(testHostComponent.galaxy.touched).toBe(false);
    expect(component.classList.contains('ng-invalid')).toBe(false);
    component.querySelector('input').dispatchEvent(new Event('blur'));
    hostFixture.detectChanges();
    expect(testHostComponent.galaxy.touched).toBe(true);
    expect(component.classList.contains('ng-invalid')).toBe(true);
  });
```

We care that the formControl element is getting the ng-touched class and touched property true.