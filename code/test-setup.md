### Test Setup

```typescript
@Component({
  template: '<gr-typeahead [data]="testData" [formControl]="galaxy"></gr-typeahead>'
})
class TestHostComponent {
  @ViewChild(TypeaheadComponent)
  public typeaheadComponent: TypeaheadComponent;
  public testData = [{id: 1, name: 'foo'},{id: 2, name: 'bar'}];
  public galaxy: FormControl = new FormControl({value: null, disabled: false});
}

describe('TypeaheadComponent', () => {
  let hostFixture: ComponentFixture<TestHostComponent>;
  let testHostComponent: TestHostComponent;

  beforeEach(async(() => {
    TestBed.configureTestingModule({
      declarations: [ TypeaheadComponent, TestHostComponent ],
      imports: [ TypeaheadModule.forRoot(), FormsModule, ReactiveFormsModule ]
    })
    .compileComponents();
  }));

  beforeEach(() => {
    hostFixture = TestBed.createComponent(TestHostComponent);
    testHostComponent = hostFixture.componentInstance;
    hostFixture.detectChanges();
  });

  it('should create', () => {
    expect(testHostComponent.typeaheadComponent).toBeTruthy();
  });
});

```

Create a test host component & use ViewChild to access CVA component
