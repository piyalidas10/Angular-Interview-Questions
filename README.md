### Table of Contents

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   |  Pure vs impure pipe
| 2   |  How will create custom pipes? Have you ever created any custom pipes in your project?
| 3   |  Observable vs observer
| 4   |  How many directives are there? <br><br> 1. Attribute 2. Structural 3. Component
| 5   |  component vs directive ? <br><br> Components are a type of Directive. @Directive is a decorator which is used to instruct the DOM to either add a new element or, remove or modify an existing element. @Component is a subclass of @Directive with one additional functionality. Using @component, you can create ou HTML template.
| 6   |  Creating custom structural directives
| 7   |  Advantage of Async pipe
| 8   |  What is Internationalization & why is used ?
| 9   |  What are the functionalities of -------- Main.js, Bundle.js, Packagelock.json
| 10   |  Deep copy vs shallow copy
| 11   |  :host & ::ng-deep
| 12   |  As we know service is singleton means it will create single instance entire application. How can I create multiple instances of services?
| 13   |  AOT vs JIT compiler
| 14   |  What do you mean by data binding & two way data binding <br><br> Types of Data Binding : 1. Interpolation & Property binding 2. Event binding 3. Two way binding <br><br> Interpolation is used to just display/bind a piece of data in HTML UI element, such as displaying a title or a name. <br><br> Property binding lets us bind a property of a DOM object, for example the hidden property, to some data value. It uses syntax []. <br><br> Event binding is used to handle the events raised by the user actions like button click, mouse movement, keystrokes, etc. It flows from the view to the model when an event is triggered. <br><br> In Two way binding, data dlows from model to view and view to model.
| 15   |  How many ways to share data one component to another
| 16   |  @ViewChild() vs @Input --- to send data from parent component to child which one 
| 17   |  Reactive form setValue vs patchValue
| 18   |  When you will use “of”
| 19   |  What is TestBed?
| 20   |  How you will test one service inside another service?
| 21   |  megeMap vs concatMap
| 22   |  Advantage of Server side rendering
| 23   |  Why use platform-browser package
| 24   |  How many guards are there
| 25   |  canLoad vs canActivate (which one is better to use)
| 26   |  How can you combine 2 data streams together and use as one observable?
| 27   |  How can you put a limit to data that you get from stream?
| 28   |  If you want to put condition on time of observable subscription, which operator should use? Suppose you 
| 29   |  If I have more than one APIs to merge to get the results but should come as sequential order as I sent them. Which operator I have to use?
| 30   |  If you have and application where you have to show user’s messages. How you will get notification of new message arrived?
| 31   |  How many ways are there for performance optimizations of your application?
| 32   |  Can I use directive as a component?
| 33   |  Angular lifecycle hooks explain with example & use
| 34   |  What Ivy and advantage is of use it ?
| 35   |  If you want to get @input() changes, which lifecycle hook will be use 
| 36   |  Purpose of Observables & how many observables are there
| 37   |  routing, guards, fragments, wild card routes
| 38   |  ng template vs ng container vs ng content
| 39   |  Have you ever worked with Dynamic component? If yes, why need this?
| 40   |  Why use “useClass” & “useValue” in provide?
| 41   |  @Inject() vs @Injectable
| 42   |  Fix the error from the bellow code <br><br> main.ts <br><br> import { enableProdMode } from '@angular/core'; <br>import { platformBrowserDynamic } from '@angular/platform-browser-dynamic'; <br> import { environment } from './environments/environment'; <br> if (environment.production) { <br>enableProdMode();<br>}<br>platformBrowserDynamic()<br>.bootstrapModule()<br>.catch((err) => console.error(err));
| 43   |  Why we need angular library? Have you worked in any library in your project?
| 44   |  Can i create multiple angular apps in one project? <br> https://www.tektutorialshub.com/angular/angular-multiple-apps-in-one-project/ <br>https://angular.io/guide/file-structure
| 45   |  useClass vs useValue
| 46   |  Have you worked in localization? What is the use of it? How it works?
| 47   |  How you will translate dynamic value using localization?
          There have two way to use localization : 1. inside HTMl using i18n 2. inside ts file $localize
          1. inside HTMl using i18n
          ```
          <button i18n="Submit|Submit the form@@FEEDBACK.USER_FEEDBACK.submit">Submit</button>
          ```
          inside messages.xlf file, the upper html code will be converted like the following:
          ```
               <trans-unit id="FEEDBACK.USER_FEEDBACK.submit" datatype="html">
                <source> Submit </source>
                <context-group purpose="location">
                  <context context-type="sourcefile">feedback.html</context>
                  <context context-type="linenumber">10.23</context>
                </context-group>
                <note priority="1" from="description">Submit the form</note>
                <note priority="1" from="meaning">Submit</note>
              </trans-unit>
         ```
         2. inside ts file $localize
         
         ```
                .html file
                <button>{{buttonLabel}}</button>
                
                .ts file
                this.buttonLabel = $localize`:Submit|Submit the form@@FEEDBACK.USER_FEEDBACK.submit`
          ```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 48   |  useClass vs useValue   
| 49   |  When you will use ngOnChanges
| 50   |  Suppose you have a component, inside it you have another child component like the following <br> app.compont.html <br> <app-child></app-child> <br> You want to access the DOM of that child component. Which life cycle hook will give you the access of that child component ?
| 51   |  What is the starting point of angular application ?
| 52   |  package.json vs package-lock.json
| 53   |  What is the use of view encapsulation?
| 54   |  Explain the @Component Decorator. <br> TypeScript class is one that is used to create components. This genre of class is then decorated with the "@Component" decorator. The decorato’s purpose is to accept a metadata object that provides relevant information about the component.  
| 55   |  Promises vs Observables
| 56   |  Subject vs BehaviorSubject
| 57   |  What are the advantages of Reactive forms over Template driven forms
| 57   |  Subject vs BehaviorSubject
| 58   |  Why need Lazy loading ?
| 59   |  How can you share data between components?
| 60   |  What is Two way data binding?
| 61   |  Is constructor a part of angular ?
| 61   |  What is Dependency Injection? <br><br> 1. Using Dependency Injection we move the creation of binding dependent object otside of the class that depend on them. 2. DI keeps the code more flexible testable and mutable. 3. Class can inherit external logic without having to create on its own. 4. DI benefits directives, pipes and components.  <br><br> Consider all the components of an application performing common tasks like accessing database, rendering images on the view etc. To avoid rewriting of code, angular services can be used. These services can then be injected into the components that require that service. 


          
        




