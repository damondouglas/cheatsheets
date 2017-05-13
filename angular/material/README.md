

# Material design

## Install

`npm install --save @angular/material`

## Setup

### `app.module.ts` setup
```ts
import {MdButtonModule, MdCheckboxModule} from '@angular/material';

@NgModule({
  ...
  imports: [MdButtonModule, MdCheckboxModule],
  ...
})
```

### `index.html`

`<link href="../node_modules/@angular/material/prebuilt-themes/indigo-pink.css" rel="stylesheet">`

### Install Gesture support

`npm install --save hammerjs`

then in `app.module.ts`:

```ts
import 'hammerjs';
```

## Use

```html

      <button md-button>FLAT</button>
      <button md-raised-button md-tooltip="This is a tooltip!">RAISED</button>
      <button md-raised-button color="primary">PRIMARY RAISED</button>
      <button md-raised-button color="accent">ACCENT RAISED</button>
```
