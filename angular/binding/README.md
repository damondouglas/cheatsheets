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

## event binding

```html
<button
(click)="onClick($event)"
>click me
</button>
```

```ts
export class MyClass {
  ...
  onClick(event) {
      ...
  }
  ...
}
```

OR

```html
<button
(click)="onClick()"
>click me
</button>
```

```ts
export class MyClass {
  ...
  onClick() {
      ...
  }
  ...
}
```
