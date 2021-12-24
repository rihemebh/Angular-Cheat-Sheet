# Angular-Cheat-Sheet

[What is Angular](#Angular) 
- [Modules](#module)
- [Components](#component)
- [Template](#template)
   - [Data binding](#data-binding)
   - [Directives](#attribute-directives)
- [Services](#services)

Angular is a Js Framework that supports multiple laguages like ES5, Typescript , dart ... <br />
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
#### Property Binding (DOM <- Component)
A one-way binding  that allows the DOM to recover data from the component. 
The property is interpreted by the framework before it is added to the template.
We can call a property using : 
1. on-property
2. [property]
#### Event Binding (DOM -> Component)
A one-way binding that allows intercations from the DOM to the components using events Handlers.
we can call a method using: <br/>
1. on-eventName
2. (eventName)

#### Tow-way Binding (DOM <-> Component)

Angular supports two-way data binding that allows interctions from DOM to component and component to DOM using directives (**ngModel**)<br />
  <!--<img src="https://github.com/rihemebh/Angular-Cheat-Sheet/blob/main/databinding.png"   alt="data-binding" />-->

```html
<li>{{hero.name}}</li>
<app-hero-detail [hero]="selectedHero"></app-hero-detail>
<li (click)="selectHero(hero)"></li>
```

- The {{hero.name}} interpolation displays the component's hero.name property value within the <li> element.

- The [hero] property binding passes the value of selectedHero from the parent HeroListComponent to the hero property of the child HeroDetailComponent.

- The (click) event binding calls the component's selectHero method when the user clicks a hero's name.
  

  
 ### Attribute directives

Angular directives are classes with the ``@Directive`` metadata. It allows you to modify the DOM and makes Templates dynamic
  
 Example of pre-defined directives: 
  - ``ngModel`` :  modifies the behavior of an existing element (typically <input>) by setting its display value property and responding to change events.
  - `` ngStyle ``
  - `` ngClass`` 
  - ``ngSwitch``

  ## services 
  
  Classes decorated by ``@Injectable()`` allowing to encapsulate business processes 
  
  ```typescript
  import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class HeroService {

  constructor() { }

}
  
  ```
  
  By default, the Angular CLI command ``ng generate service`` registers a provider with the root injector for your service by including provider metadata, that is ``providedIn: 'root'`` in the ``@Injectable()`` decorator.
  
  
