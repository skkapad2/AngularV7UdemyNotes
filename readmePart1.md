# Angular v7 Notes
<!-- TOC -->
- [Hello Angular](#hello-angular)
- [The Basics](#the-basics)

<!-- /TOC -->
# Hello Angular
- app.component.html
```html
<div style="text-align:center">
  <h1>
    Hi, this is {{ title }}!
  </h1>
  <img width="300" alt="Angular Logo" src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNTAgMjUwIj4KICAgIDxwYXRoIGZpbGw9IiNERDAwMzEiIGQ9Ik0xMjUgMzBMMzEuOSA2My4ybDE0LjIgMTIzLjFMMTI1IDIzMGw3OC45LTQzLjcgMTQuMi0xMjMuMXoiIC8+CiAgICA8cGF0aCBmaWxsPSIjQzMwMDJGIiBkPSJNMTI1IDMwdjIyLjItLjFWMjMwbDc4LjktNDMuNyAxNC4yLTEyMy4xTDEyNSAzMHoiIC8+CiAgICA8cGF0aCAgZmlsbD0iI0ZGRkZGRiIgZD0iTTEyNSA1Mi4xTDY2LjggMTgyLjZoMjEuN2wxMS43LTI5LjJoNDkuNGwxMS43IDI5LjJIMTgzTDEyNSA1Mi4xem0xNyA4My4zaC0zNGwxNy00MC45IDE3IDQwLjl6IiAvPgogIDwvc3ZnPg==">
</div>
<h2>Here are some links to help you start: </h2>
<ul>
  <li>
    <h2><a target="_blank" rel="noopener" href="https://angular.io/tutorial">Tour of Heroes</a></h2>
  </li>
  <li>
    <h2><a target="_blank" rel="noopener" href="https://angular.io/cli">CLI Documentation</a></h2>
  </li>
  <li>
    <h2><a target="_blank" rel="noopener" href="https://blog.angular.io/">Angular blog</a></h2>
  </li>
</ul>
``` 
- app.component.ts
```typescript
/**
* export class AppComponent title can be used 
*/
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'my app buddy';
}
```

# The Basics
Index.hmtl file is served by the server not app.component.html. 
* Approot tages actually are in the file below and the temlate URL/path is what allows the tag to get the data from.
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root', //html tag
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  
}
```
main.ts gets executed first, and then bootstrap angular application and module as an argument and there is an app component that you should analyze. Finally Angular can handle app root in the index.html  

```typescript
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

import { AppModule } from './app/app.module';
import { environment } from './environments/environment';

if (environment.production) {
  enableProdMode();
}

platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err));
  ```
  # Components
  * To create a component : ng generate component servers
    * Ex: servers component. html place tags or whatever you want to write. From there, in the app.component.html you can place selector tags to output things.
```typescript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-servers',
  template: '<app-server></app-server><app-server></app-server>', //switched to template so that can do inline things
  styleUrls: ['./servers.component.css']
})
export class ServersComponent implements OnInit {

  constructor() { }

  ngOnInit() {
  }

}
``` 



