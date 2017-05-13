# Material design

from: https://material.angular.io/guide/getting-started

## Install

`npm install --save @angular/material`

`npm install --save @angular/animations`

## Setup

### create material module

`ng g m material --spec false`

### app/material/material.module.ts

```
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import {BrowserAnimationsModule} from '@angular/platform-browser/animations';
import {
  // IMPORT each material element you want to use here
  MdButtonModule
} from '@angular/material';

@NgModule({
  imports: [
    CommonModule,
    BrowserAnimationsModule,
    MdButtonModule,
  ],
  exports: [
    // REMEMBER TO EXPORT!
    MdButtonModule
  ],
  declarations: []
})
export class MaterialModule { }

```


### index.html

`<link href="../node_modules/@angular/material/prebuilt-themes/indigo-pink.css" rel="stylesheet">`

### Install Gesture support

`npm install --save hammerjs`

### app.module.ts:

```
import 'hammerjs';
import { MaterialModule } from './material/material.module';

@NgModule({
  ...
  imports: [
    MaterialModule
  ],
})
```

## Use

see https://material.angular.io/components for list of components available.

```html

      <button md-button>FLAT</button>
      <button md-raised-button md-tooltip="This is a tooltip!">RAISED</button>
      <button md-raised-button color="primary">PRIMARY RAISED</button>
      <button md-raised-button color="accent">ACCENT RAISED</button>
```
