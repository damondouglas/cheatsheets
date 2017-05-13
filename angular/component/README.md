
# Components

## selector can be any css selector
```angular
@Component(
  selector: '<element name>' or '.<class name>' or '[attribute]'
)
```

### Examples:

```angular
@Component(
  selector: 'app-main'
)
```
applies to: `<app-main></app-main>`

```angular
@Component(
  selector: '.some-class'
)
```

applies to:

```html
  <div class="some-class"></div>
  <p class="some-class"></p>
```
