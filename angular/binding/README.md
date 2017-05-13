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

# Two-way data binding

```ts
export class SomeComponent {
	myProperty = "";
}
```

```html
<input
[(ngModel)]="myProperty"
>

<div>{{myProperty}}</div>
```

IMPORTANT: In order for this to work you must have `FormsModule` in `imports[]` array in `AppModule`.

```ts
import { FormsModule } from '@angular/forms';

@NgModule({
  ...
  imports: [
    FormsModule,
  ],
})
```
