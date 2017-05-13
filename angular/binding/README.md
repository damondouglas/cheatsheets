# Binding

## property binding

```ts
@Component(...)
export class SomeComponent {
  shouldBeDisabled:boolean = true;
}
```

```html
  <button [disabled]="shouldBeDisabled">click me</button>
```
