# *ngIf and else

```html
<p *ngIf="somethingIsTrue; else somethingIsNotTrueRef">Output if something is true</p>
<ng-template #somethingIsNotTrueRef">
  <p>Output if something is not true.</p>
</ng-template>
```

# ngClass

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
