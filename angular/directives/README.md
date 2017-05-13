# *ngIf and else

```html
<p *ngIf="somethingIsTrue; else somethingIsNotTrueRef">Output if something is true</p>
<ng-template #somethingIsNotTrueRef">
  <p>Output if something is not true.</p>
</ng-template>
```
