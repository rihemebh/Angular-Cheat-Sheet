# Angular-Cheat-Sheet

Angular is a Js Framework that supports multipl laguages like ES5, Typescript , dart ... <br />
- SPA (Single Page application):
The single page application is a web application or website that interacts with the user by dynamically rewriting the current page, rather than loading entire new pages from the server.

- Modular , fast , component based

## Module 
a Module is a class that is decorated by ``@NgModule``
appModule is the main module that is in charge of the application bootstrapping 

```typescript 
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';
@NgModule({
imports: [ BrowserModule ], /* List of modules to be used */
declarations: [ AppComponent ], /*list of components + directives + pipes  */
bootstrap: [ AppComponent ] / *the component to be executed when the application is launched*/
})
export class AppModule { }
```


## Component 

A component is a class decorated by ``@Component``

```typescript
@Component({
  selector: 'app-component-overview', /* A selector instructs Angular to instantiate this component wherever it finds the corresponding tag in template HTML */
  templateUrl: './component-overview.component.html', /*associates a template with the component*/
  styleUrls: ['./component-overview.component.css'] ,
   providers:  [ HeroService ] /* An array of providers for services that the component requires*/
})
```

## Template 

A template is the view (HTML file) associated to a specific component 

### Data binding 
Data binding is the mecanism that allows a component and its template to communicates with each others 

Angular supports two-way data binding <br />
<img src="https://github.com/rihemebh/Angular-Cheat-Sheet/blob/main/databinding.png"   alt="data-binding" />
### Event binding 
