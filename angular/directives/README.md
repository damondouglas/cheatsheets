# *ngIf and else

```html
<p *ngIf="somethingIsTrue; else somethingIsNotTrueRef">Output if something is true</p>
<ng-template #somethingIsNotTrueRef">
  <p>Output if something is not true.</p>
</ng-template>
```

# ngClass

IMPORTANT: No star `*` in front of `ngClass`.

Template:

```html
<p [ngClass]="{foo: isFooTrue}"></p>
```

Output if `isFooTrue=true`:

```html
<p class="foo"></p>
```

OR

Template:

```html
<p [ngClass]="{foo: fooProperty === 'foo'}"></p>
```

Output if `foo` is the value `"foo"`:

```html
<p class="foo"></p>
```

# *ngFor

typescript:
```
nameList = [
  'foo',
  'bar',
  'baz'
];
```

```html
<div *ngFor="let name of nameList">{{name}}</div>
```

yields:

```html
<div>foo</div>
<div>bar</div>
<div>baz</div>
```

# *ngFor and index

typescript:
```
nameList = [
  'foo',
  'bar',
  'baz'
];
```

```html
<div *ngFor="let name of nameList; let i = index">{{i}}: {{name}}</div>
```
IMPORTANT: it's `=` and not `of` when using `let i = index`.

yields:

```html
<div>0: foo</div>
<div>1: bar</div>
<div>2: baz</div>
```

# ngStyle and index

```html
<div
  *ngFor="let name of nameList; let i = index"
  [ngStyle]="{backgroundColor: i % 2 === 0 ? 'blue' : 'red'}">{{i}}: {{name}}</div>
```

yields:

```html
<div>0: foo</div>
<div>1: bar</div>
<div>2: baz</div>
```
