# property binding

```ts
@Component(...)
export class SomeComponent {
  shouldBeDisabled:boolean = true;
}
```

```html
  <button [disabled]="shouldBeDisabled">click me</button>
```

# event binding

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

# custom event binding

## Child component

```
import {
  Component, OnInit,
  Input,
  Output,
  EventEmitter
} from '@angular/core';

@Component({
  selector: 'app-child',
  templateUrl: './child.component.html',
  styleUrls: ['./child.component.css']
})
export class ChildComponent implements OnInit {
  @Output() timeout = new EventEmitter<{name: string, timestamp: Date}>();;
  constructor() { }

  ngOnInit() {
    setTimeout(() => {
      this.timeout.emit({
        name: 'foo',
        timestamp: new Date()
      });
    }, 1000);
  }
}
```

## Parent component

```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  doSomething(event) {
    console.log(event);
  }
}
```

```html
<app-child (timeout) = "doSomething($event)"></app-child>
```

Consule output:
```
Object {name: "foo", timestamp: Sat May 13 2017 18:28:58 GMT-0700 (PDT)}
```
