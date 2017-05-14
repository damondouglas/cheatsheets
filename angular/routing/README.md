```
import { Routes, RouterModule } from '@angular/router';

const appRoutes: Routes = [
  { path: '', component: HomeComponent},
  { path: 'users', component: UsersComponent },
  { path: 'servers', component: ServersComponent},
];


@NgModule({
  ...
  imports: [
    RouterModule.forRoot(appRoutes)
  ],
})
```

```html
<li role="presentation" class="active"
  <!-- prevents always setting root path to be active !>
  [routerLinkActiveOptions]="{exact: true}"
><a routerLink="/">Home</a></li>
<li role="presentation"><a routerLink="/servers">Servers</a></li>
<li role="presentation"><a routerLink="/users">Users</a></li>

...
...
...

<router-outlet>
```

# Programmatically route app

```
import {Router } from "@angular/router";

...
this.router.navigate(['/servers']);
import {Router } from "@angular/router";

...
this.router.navigate(['/servers']);
...

```

# url parameters

In app.module.ts:

```
const appRoutes: Routes = [
  { path: 'users/:id', component: UserComponent },
]
```

In component.ts:

```
import { ActivatedRoute }  from "@angular/router";

ngOnInit() {
  this.id = this.route.snapshot.params['id']
  // do somehting with this.id
}
```

# subscribe to route changes

```
this.route.params
.subscribe(
  (params: Params) => {
    this.user.id = params['id'];
  }
);
```

# bind routerLink property to array

IMPORTANT to put `[routerLink]` in `[]`.
<a [routerLink]="['/users', 49]">user</a>

# query params and fragment

`/users/49?allowEdit=1#loading`

IMPORTANT remember the `"'loading'"` inner quotation.

```html
<a
[routerLink]="['/users', 49]"
[queryParams]="{allowEdit: '1'}"
[fragment]="'loading'"
>user</a>
```

```
this.route.navigate(
  ['/users', 49],
  {
    queryParams: {allowEdit: '1'},
    fragment: 'loading'
  }
);
```
