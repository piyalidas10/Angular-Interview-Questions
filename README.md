### Table of Contents

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   |  What is Pipe ? Pure vs impure pipe ? <br><br> Pipes help you to transform data from one format to another format. There have few inbuilt pipes in angular : DatePipe, CurrencyPipe, UpperCasePipe, LowerCasePipe, JsonPipe. <br><br> An impure pipe is called for every change detection cycle no matter whether the value or parameter(s) changes. A pure pipe is only called when Angular detects a change in the value or the parameters passed to a pipe.
| 2   |  How will create custom pipes? Have you ever created any custom pipes in your project?
| 3   |  Observable vs observer
| 4   |  How many directives are there? <br><br> 1. Attribute (pipe, format changer etc) 2. Structural (ngIf, ngFor) 3. Component (angular component)
| 5   |  component vs directive ? <br><br> Components are a type of Directive. @Directive is a decorator which is used to instruct the DOM to either add a new element or, remove or modify an existing element. @Component is a subclass of @Directive with one additional functionality. Using @component, you can create ou HTML template.
| 6   |  Creating custom structural directives
| 7   |  Advantage of Async pipe ? <br/> Automatically handling subscriptions and taking care of memory leaks. Async pipe is really powerfull with NgRx.
| 8   |  What is Internationalization & why is used ? <br/> Internationalization (i18n) in Angular is the process of designing and preparing your Angular application to support multiple languages without changing the source code. @angular/localize package is required to install. <br/> 1. Angular uses special attributes (i18n) in text elements (<h1 i18n="Card Header|Title for the under construction card">Under Construction!</h1>) <br/> 2. $localize() function directly write in ts file ($localize`Created by ${this.company}`) . 
| 9   |  What are the functionalities of Main.js, Polyfills.js, Vendor.js, Runtime.js, Package-lock.json ? <br/><br/> 1. <b>Main.js</b> - Entry point of your Angular application which contains the bootstrap logic that initializes and launches your Angular application, the application code, including all the components, services, and modules of your Angular application. It includes the necessary code to set up the application environment, load the required modules, and configure the application for rendering in the browser. It also handles other essential tasks such as registering service workers for progressive web apps (PWAs) and enabling production optimizations like AOT (Ahead-of-Time) compilation. <br/> 2. <b>Polyfills.js</b> - Contains the scripts in order to make the application compatible to different browsers <br/> 3. <b>Vendor.js</b> - Contains all Angular + 3rd party libraries in it. It includes packages like Angular itself, RxJS, and other external libraries that your app relies on. <br/> 4. <b>Runtime.js</b> - It provides the runtime environment necessary for the execution of your application. The file contains the core Angular runtime code, which enables Angular-specific functionalities such as change detection, dependency injection, and routing. <br/> 5. <b>Package-lock.json</b> - lock down the exact versions of every package and its dependencies that are installed in your project. The package-lock. json file is an automatically generated file in Angular projects, created when you first run npm install.
| 10   |  Uses of Angular platform-browser module ? <br/><br/> 1. Supports execution of Angular apps on different supported browsers. <br/> 2. The BrowserModule is included by default in any app created through the CLI, and it re-exports the CommonModule and ApplicationModule exports, making basic Angular functionality available to the app. Bootstrapping is essential feature to render a standalone component as the application's root component using bootstrapApplication(App). <br/> 3. <b>By</b> (Class) - use with DebugElement's query functions in Jasmine Unit testcase for HTML Emements. const btn: HTMLElement = DebugElement.query(By.css('.btn'))); btn.triggerEventHandler('click', {}); <br/> 4. <b>DomSanitizer</b>  (Class) - helps preventing Cross Site Scripting Security bugs (XSS) by sanitizing values to be safe to use in the different DOM contexts. <br/> 5. <b>Meta</b>  (Class) - for managing HTML <meta> tags like add, delete, update (browser's meta data). <br/> 6. change the title of the page dynamically. <br/> 7. angular/platform-browser/animations - Provides infrastructure for the rendering of animations in supported browsers.
| 11   |  :host & ::ng-deep <br><br> applied directly to the ap-root element only
        :host h2 {
            color: red;
        }
        
        ::ng-deep cascade to all child elements of a component, but not to any other element on the page, we can currently do so using by combining the :host with the ::ng-deep selector:
        :host ::ng-deep h2 {
            color: red;
        }
        :host-context ==> we also want to have a component apply a style to some element outside of it. This does not happen often, but one possible common use case is for theme enabling classes.

        For example, let's say that we would like to ship a component with multiple alternative themes. Each theme can be enabled via adding a CSS class to a parent element of the component.

        Here is how we could implement this use case using the :host-context selector:
        @Component({
          selector: 'themeable-button',
          template: `
                <button class="btn btn-theme">Themeable Button</button>
          `,
          styles: [`
              :host-context(.red-theme) .btn-theme {
                background: red;
              }
              :host-context(.blue-theme) .btn-theme {
                  background: blue;
              }
          `]
        })
        export class ThemeableButtonComponent {

        }
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 12   |  As we know service is singleton means it will create single instance entire application. How can I create multiple instances of services? Ans. Have to remove providedIn: "root" from the service & import it in the components directly (@Component({inside providers}) or @Inject()) for multiple instances.
```
constructor(
    @Inject('instance1') private service1: DataService,
    @Inject('instance2') private service2: DataService,
  )
```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 13   |  AOT vs JIT compiler <br/><br/> https://www.monarch-innovation.com/aot-vs-jit-compiler-in-angular
| 14   |  What do you mean by data binding & two way data binding <br><br> Types of Data Binding : 1. Interpolation & Property binding 2. Event binding 3. Two way binding <br><br> Interpolation is used to just display/bind a piece of data in HTML UI element, such as displaying a title or a name. <br><br> Property binding lets us bind a property of a DOM object, for example the hidden property, to some data value. It uses syntax []. <br><br> Event binding is used to handle the events raised by the user actions like button click, mouse movement, keystrokes, etc. It flows from the view to the model when an event is triggered. <br><br> In Two way binding, data flows from model to view and view to model.
| 15   |  How many ways to share data one component to another ? <br/><br/> 1. <b>Parent-to-Child</b>: Sharing Data via @Input. <br/> 2. <b>Child-to-Parent</b>: Sharing Data via @Output() and EventEmitter. <br/> 3. <b>Unrelated Components</b>: Sharing Data via a Service.  <br/> 4. <b>Child-to-Parent</b>: Sharing Data via ViewChild.
| 16   |  @ViewChild vs @Input/@Output --- @ViewChild is a decorator that allows a component to access a child component(like methods or access instance variables that are available to the child), directive, or DOM element. @Input() and @Output() are decorators that allow a component to share data with its parent or child components.
| 17   |  Reactive form setValue vs patchValue ? <br/> setValue - if we want to set the value of one control, this will not work, therefor we have to set the value of both controls: formgroup.setValue({name: ‘Mocrosoft’, age: ‘25’}); It is necessary to mention all the controls inside the method. If this is not done, it will throw an error. <br/> patchValue - patchvalue is a lot easier on that part, let’s say we only want to assign the name as a new value: formgroup.patchValue({name:’Mocrosoft’}); See how we exclude age and this will work without throwing any errors.
| 18   |  Rxjs operators (of vs from) and when you will use them ? Ans. both the of and from operators are used for creating observables. but 1. <b>of</b> operator - takes any number of arguments and emits each argument as a separate notification. It can be used to create an observable sequence from a variety of different sources, including arrays, strings, and objects. 2. <b>from</b> operator - can only take a single argument. The from operator will convert the argument to an observable sequence and emit each value in the sequence as a separate notification.
| 19   |  @ViewChild and ElementRef for DOM manipulation ? <br/><br/> Ans. <b>ViewChild</b> - safe to use when used properly. Angular ensures that ViewChild references are initialized after the view has been initialized, making it a safe way to access child components or DOM elements. ViewChild with components that use content projection (ng-content). <br/> <b>ElementRef</b> - Angular ElementRef is a wrapper around a native DOM element (HTML element) object. It contains the property nativeElement, which holds the reference to the underlying DOM object. We can use it to manipulate the DOM. We use the ViewChild to get the ElementRef of an HTML element in the component class. Tt should be used with caution, as it bypasses Angulars change detection.
| 20   |  Enable/Disable Angular Reactive form input boxes based on checkbox check & uncheck ? <br/><br/> 1. scenario 1 -> make disable: true with formCOntrol & then subscribe the change(true/false) using form checkbox valueChanges <br/> 2. scenario 2 -> make disable: true with formCOntrol & then include change function((change)="isChecked($event)") in checkbox to detect the change(true/false) <br/> <br/> [https://angular-ivy-wshce9.stackblitz.io](https://stackblitz.com/edit/angular-ivy-wshce9?file=src%2Fapp%2Fapp.component.html)
| 21   |  mergeMap, switchMap, concatMap, exhaustMap, forkjoin in rxjs
          ```1. mergeMap - It takes an observable and maps each emitted value to another observable, then subscribes to all the mapped observables and emits their values as they arrive. The emitted values are merged into a single stream, which means that they can arrive out of order. It is mainly useful for handling concurrent operations that may emit values in any order.
          2. concatMap - It is similar to mergeMap, but it subscribes to each mapped observable sequentially, waiting for each to complete before subscribing to the next one. The emitted values are concatenated into a single stream, which means that they will arrive in the order in which they were emitted. ConcatMap is useful when you need to maintain the order of emitted values.
          3. switchMap - for any source item, completes the previous Observable and immediately creates the next one. Cancel first one, immediately trigger latest one.
          4. exhaustMap - source items are ignored while the previous Observable is not completed
          5. forkjoin - It is an operator that takes multiple observables and waits for all of them to complete before emitting an array of their last emitted values. If any of the input observables emit an error, the combined observable will also emit an error immediately. It’s useful when you need to perform several operations in parallel and combine their results into a single value.
          ![MergeMap_ConcatMap_ForkJoin](MergeMap_ConcatMap_ForkJoin.png)
          ```

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |  
| 22   |  Server side rendering vs Client side rendering ? <br/><br/> Ans. https://v17.angular.io/guide/ssr                                                                

| Sl. No.           | Client-side rendering                                              | Server-side rendering                                         |
| ----------------- | ------------------------------------------------------------------ | --------------------------------------------------------------|
| Rendering process | Rendering process occurs on the browser using JavaScript           | Rendering process occurs on the server                        |
| SEO | Harder for search engines to crawl and index content           | Easier for SEO as search engines can crawl rendered HTML                        |
| Initial page load | Initially loads an HTML shell, then JavaScript bundle is fetched and executed to render the UI | Initially loads a fully rendered HTML page from the server |
| Initial page load experience | User sees a blank page or loading spinner until the JavaScript bundle is downloaded and executed| User sees the rendered content immediately upon page load|
| Type of application | Ideal for SPAs, highly interactive web apps like social media platforms and chat apps, and internal apps user dashboards| Ideal for content-heavy websites and apps with limited interactivity requirements like landing pages, ecommerce apps, documentation, and media publications|
| Framework that support it | Frameworks include React, Angular, Vue, Svelte, Backbone.js, and Ember.js| Frameworks include Next.js, Nuxt.js, Remix, SvelteKit, Angular Universal, Astro, and Qwik. Note that some of these frameworks also support CSR.|
| Interactivity | Highly interactive and responsive after the initial load, as subsequent interactions are handled client-side without requiring full page refreshes| Initial interactivity is limited to the pre-rendered content; subsequent interactions may require full page refreshes or client-side rendering|
| Loading speed | Slower initial load time due to fetching and parsing JavaScript files | Faster initial load time as HTML is pre-rendered |
| Caching | Difficult to cache rendered pages | Easier to cache rendered HTML pages on servers or CDNs |
| Data fetching | Data is fetched via API calls after the initial load| Data is fetched on the server |
| Server load | Reduced server load since rendering occurs on the browser | Increased server load since rendering occurs on the server |
| HTTP requests | Makes fewer HTTP requests to the server| Requires more HTTP requests to the server|
| JavaScript dependency | Depends heavily on JavaScript | Minimal JavaScript dependency |

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 23   |  How will prevents unnecessary api calls angular ? <br/><br/> Ans. Debounce should be used. The debounceTime allows to buffer events and only handle the last one after an amount of time. It's useful in the context of inputs but it should be defined on the observable that triggers the event not on the one created for the HTTP request. Here is a example on a control associated with an input that leverages the debounceTime operator: 
        ```@Component({
          (...)
          template: `
            <input [ngFormControl]="ctrl"/>
          `
        })
        export class MyComponent {
          constructor() {
            this.ctrl = new Control();
            this.ctrl.valueChanges
                       .debounceTime(500)
                       .distinctUntilChanged()
                       .switchMap((value: string) => {
                         // Get data according to the filled value
                         return this.service.getData(entry);
                       })
                       .subscribe(data => {
                         // Update the linked list
                         this.list = data;
                       });
          }
        }
        ```
        

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 24  |  How many guards are there ? https://raghuvardhankaranam.medium.com/route-guards-in-angular-c2c01fe6167b
| 25  |  canLoad vs canActivate (which one is better to use) ? <br/> Ans. canActivate is used to prevent unauthorized users from accessing certain routes. canLoad is used to prevent the application from loading entire modules lazily if the user is not authorized to do so.
| 26   |  How can you combine 2 data streams together and use as one observable? <br/> Ans. Rxjs forkjoin operator & promise.all
| 27   |  How can you put a limit to data that you get from stream? <br/> Ans. Rxjs take operator
| 28   |  If you want to put condition on time of observable subscription, which operator should use? <br/> Ans. Rxjs timer operator
| 29   |  If I have more than one APIs to merge to get the results but should come as sequential order as I sent them. Which RXJS operator I have to use? <br/> Ans. ConcatMap 
| 30   |  If you have and application where you have to show user’s messages. How you will get notification of new message arrived? <br/><br/> 1) Sending Push Notifications from the Backend (Node) using webpush library. Here Need to create a REST endpoint, that when triggered will result in a notification to be sent to all subscribers. The endpoint would have to be protected by both authentication and authorization middleware. <br/> 2) Angular Service Worker to correctly display the message, we need to use proper format. Namely, we will the payload to be one root object containing one property named notification, otherwise the messages will not be displayed to the user. Once we have the message payload ready, we can send it to a given subscriber via a call to webpush.sendNotification(). <br/> 3) When the Push service receives the message, it will know to which browser instance to forward the message to based on the unique url of the endpoint. Once the Push Service pushes the message to the user browser, the message is then going to be decrypted and passed to the Angular Service Worker (PWA). The Angular Service Worker will then use the browser Notifications API to display a Notification to the user. Besides the text and image of the notification, we can also specify a mobile vibration pattern via the vibrate property.
| 31   |  How many ways are there for performance optimizations of your application? <br/><br/> 1. Tree Shaking to Reduce Bundle Size - In Angular, Tree Shaking is used to decrease the size of JavaScript’s bundle. Tree shaking removes unused code from the application and shifts it into a smaller, more efficient bundle. if you are using Angular CLI, you can make it default. To enable tree shaking in an Angular application, you can use the following command in the Angular CLI: ng build --prod --optimization=true --build-optimizer=true <br/> 2. Use trackBy in ngFor loops - Angular’s ngFor directive is used to iterate over arrays and display the data on the page. Using the trackBy function will improve the rendering of the list. <br/> 3. Use lazy loading - Lazy loading modules improve the initial load time of the application by only loading the necessary components when they are needed. <br/> 4. Avoid using ngIf with complex expressions - Instead of using a complex ngIf expression, use ngSwitch for better performance. <br/> 5. Use OnPush change detection strategy - By using the OnPush change detection strategy, Angular will only check for changes when the input changes, rather than every time there is a change in the application. <br/> 6. Use immutable data structures - Immutable data structures improve the performance of the application by preventing unnecessary data manipulation like Object.freeze. An immutable data structure is valuable for optimizing change detection in Angular applications. It refers to the data that cannot be changed after creation. By using immutability data, developers can ensure that the application’s data model is updated when necessary and helps to improve overall performance. <br/> 7. Use AOT compilation - Ahead of Time (AOT) compilation improves the application’s performance by compiling the template code during the build process. ng build --aot <br/> 8. Use Angular Universal for server-side rendering - Angular Universal allows the application to be rendered on the server, improving performance for users with slow connections. <br/> 9. Use NgRx for state management - NgRx is a state management library for Angular that improves the performance of the application by providing a single source of truth for the application state. <br/> 10. Use Web Workers - Web Workers run scripts in the background, improving the performance of the application by offloading CPU-intensive tasks to a separate thread. <br/> Pure Pipes - Pips are divided into categories: Impure and Pure Pipes. Use Pure Pipes transforms data before it is displayed to the users. Not all pipes are created equally regarding the change detection performance. By using pure pipes, you can decrease the number of unnecessary change cycles. @Pipe({  name: 'myPurePipe', pure: true }) <br/> 11. Avoiding Expensive Operations in Templates - Avoiding expensive operations is crucial as it impacts the application’s performance. Also, to avoid operations in templates, you should keep templates as simple as possible to improve performance. it means that you are avoiding complex logic and computations in templates and moving them to component services. <br/> 12. Proper Usage of ngZone - <br/> 13. Minimizing the Number of HTTP Requests - Each HTTP request made by Angular includes TCP connection establishment, DNS resolution, and TLS negotiation. This will improve Angular performance significantly. Also, one of the best practices to minimize HTTP requests is to use caching. <br/> 14. Use RxJS Pipes for Frequent Data Updates like DistinctUntilChanged, DebounceTime
| 32   |  Can I use directive as a component?
| 33   |  Angular lifecycle hooks explain with example & use
| 34   |  What Ivy and advantage is of use it ? <br/><br/> Ans. Ivy enables tree shaking, a process that eliminates unnecessary code from the compiled output. This makes the code smaller, and the application runs faster. Starting from version 9 of Angular, your TypeScript code will be compiled using Ivy instead of the older ViewEngine (VE). Ivy decreases your bundle sizes, enhances testing, and improves debugging capabilities. In addition, Ivy uses Ahead-of-Time compilation to speed up your apps.
| 35   |  If you want to get @input() changes, which lifecycle hook will be use ? <br/> Ans. ngOnChanges()
| 36   |  Purpose of Observables & how many observables are there ? <br/><br/> Ans. Observables are a technique for event handling, asynchronous programming, and handling multiple values emitted over time. The observer pattern is a software design pattern in which an object, called the subject, maintains a list of its dependents, called observers, and notifies them automatically of state changes.
| 37   |  routing, guards, fragments, wild card routes ? <br/><br/> 1. Routes - ActivatedRoute provides access to information about a route associated with a component that is loaded in an outlet. Use to traverse the RouterState tree and extract information from nodes. <b>queryParams</b> is an observable of the query parameters shared by all the routes. <b>fragment</b> is an observable of the URL fragment shared by all the routes. <b>data</b> is An observable of the static and resolved data of this route. <b>snapshot: ActivatedRouteSnapshot</b> is the current snapshot of this route <br/> https://v17.angular.io/api/router/ActivatedRoute <br/><br> 2. Route guards -  provide a way to control access to certain routes based on specific conditions, enabling authentication and authorization. <b>Wildcard routes</b> handle undefined or non-existent routes, allowing you to display custom error pages or fallback content. https://raghuvardhankaranam.medium.com/route-guards-in-angular-c2c01fe6167b#:~:text=One%20of%20the%20ways%20Angular,then%20you've%20encountered%20guards. <br/>
| 38   |  ng template vs ng container vs ng content ? <br/><br/> 1. <ng-template></ng-template> - As the name suggests the <ng-template> is a template element that Angular uses with structural directives ( *ngIf, *ngFor, [ngSwitch], and custom directives). These template elements only work in the presence of structural directives, which help us to define a template that doesn’t render anything by itself, but conditionally renders them to the DOM. It helps us create dynamic templates that can be customized and configured. <br/> 2. <ng-container></ng-container> - ng-container is an extremely simple directive that allows you to group elements in a template that doesn’t interfere with styles or layout because Angular doesn’t put it in the DOM. This is helpful if you don’t want any extra div on DOM, you can simply use ng-container. <br/> 3. <ng-content></ng-content> - ng-content is used to project content into Angular components. You use the <ng-content></ng-content> tag as a placeholder for that dynamic content, then when the template is parsed Angular will replace that placeholder tag with your content.For example, you have two components as parent and child component and want to show some data in the child component from the parent component. <br/><br/> https://vibhas1892.medium.com/difference-between-ng-template-ng-container-and-ng-content-a1d264619655
| 39   |  Have you ever worked with Dynamic component? If yes, why need this? <br/><br/> Ans. Dynamic Components allow us to create and render components at runtime. Dynamic Components can be used to make the way we render our components across the frontend more flexible and dynamic.
| 40   |  Why use “useClass” & “useValue” in provider? <br/> https://medium.com/@matsal.dev/angular-usevalue-useclass-useexisting-and-usefactory-in-a-nutshell-97db8d206084
| 41   |  @Inject() vs @Injectable ? <br/><br/> Ans. @Injectable is a decorator in Angular used to mark a class as an injectable that allows it to be provided and injected as a dependency within other Angular components, services, or modules. @Injectable({  providedIn: 'root',}) <br/> <br/> @Inject is a decorator used to specify the token (dependency) to be injected into a class constructor or a provider definition.  export class MyComponent {  constructor(@Inject(ServiceClass) private myService: ServiceClass) {} }
| 42   |  Fix the error from the bellow code <br><br> main.ts <br><br> import { enableProdMode } from '@angular/core'; <br>import { platformBrowserDynamic } from '@angular/platform-browser-dynamic'; <br> import { environment } from './environments/environment'; <br> if (environment.production) { <br>enableProdMode();<br>}<br>platformBrowserDynamic()<br>.bootstrapModule()<br>.catch((err) => console.error(err));
| 43   |  Why we need angular library? Have you worked in any library in your project?
| 44   |  Can i create multiple angular apps in one project? <br> https://www.tektutorialshub.com/angular/angular-multiple-apps-in-one-project/ <br>https://angular.io/guide/file-structure
| 45   |  Metadata with a Decorator in Angular ? <br/><br/> https://www.pluralsight.com/resources/blog/guides/defining-metadata-with-a-decorator-in-angular#:~:text=The%20whole%20purpose%20of%20Angular,component%20has%20a%20specific%20configuration.
| 46   |  Difference between declarations, providers, and import in NgModule ? <br/><br/> 1. Declarations - Used to declare components, directives, pipes that belongs to the current module. 2. Providers - Used to inject the services required by components, directives, pipes in our module. 3. Imports - Used to import supporting modules
| 47   |  Have you worked in localization? What is the use of it? How it works? How you will translate dynamic value using localization?
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
| No.  | Questions                                                                                                                                                         |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 48   |  useClass vs useValue   
| 49   |  When you will use ngOnChanges
| 50   |  Suppose you have a component, inside it you have another child component like the following <br> app.compont.html <br> <app-child></app-child> <br> You want to access the DOM of that child component. Which life cycle hook will give you the access of that child component ?
| 51   |  What is the starting point of angular application ?
| 52   |  package.json vs package-lock.json
```
~version	Approximately equivalent to version, i.e., only accept new patch versions
^version	Compatible with version, i.e., accept new minor and patch versions
version	        Must match version exactly
>version	Must be greater than version
>=version	Must be equal or greater than version
<version	Must be lesser than version
<=version	Must be equal or lesser than version
1.2.x	        1.2.0, 1.2.1, etc., but not 1.3.0
*	        Matches any version
latest	        Obtains latest release
```

| No.  | Questions                                                                                                                                                         |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 53   |  What is the use of view encapsulation?
| 54   |  Explain the @Component Decorator. <br> TypeScript class is one that is used to create components. This genre of class is then decorated with the "@Component" decorator. The decorato’s purpose is to accept a metadata object that provides relevant information about the component.  
| 55   |  Promises vs Observables
| 56   |  Subject vs BehaviorSubject
| 57   |  What are the advantages of Reactive forms over Template driven forms
| 58   |  Why need Lazy loading ?
| 59   |  How can you share data between components?
| 60   |  What is Two way data binding?
| 61   |  Is constructor a part of angular ?
| 62   |  What is Dependency Injection? <br><br> 1. Using Dependency Injection we move the creation of binding dependent object otside of the class that depend on them. 2. DI keeps the code more flexible testable and mutable. 3. Class can inherit external logic without having to create on its own. 4. DI benefits directives, pipes and components.  <br><br> Consider all the components of an application performing common tasks like accessing database, rendering images on the view etc. To avoid rewriting of code, angular services can be used. These services can then be injected into the components that require that service. 
| 63   |  What is Webpack? <br><br> Webpack is a module bundler that lets you compile JavaScript modules (Files, Images, Fonts, JS, CSS, HTML, etc.). Webpack offers multiple functions, like merging modules, code minimization (or minimizing code by eliminating spaces, remarks, junk code, and code reduction), SASS or TypeScript compiling, integration with npm, and other features.

          https://flatlogic.com/blog/what-is-webpack-flatlogic-glossary/

          Webpack is also able to handle multiple other tasks:

          1. Assists in pulling your resources all together;
          2. Monitors changes and re-runs tasks;
          3. Can transpile using Babel’s next-generation JavaScript to an older JavaScript standard (ES5), allowing users to use the latest JavaScript features without worrying about whether or not their browser supports them;
          4. Does CoffeeScript to JavaScript translation;
          5. Can converse embedded images into data: URI;
          6. can require() CSS files;
          7. Works with Hot Module Replacement;
          8. May Perform Tree Shaking;
          9. Can split output file into several files so slow page load due to oversized JS-file is prevented.

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 63   |  Is Webpack needed for Angular? <br><br> While the primary purpose of Webpack is to build multiple modules into a single file, it is not bound to only bundling source files. <br> Usually, webpack is hidden behind the Angular command-line tool. Webpack is used internally by angular application to compile ts files ino a single js file.
| 64   | What benefits does Webpack 5 bring to Angular 12? <br><br> I understand the build time is increased for you with webpack 5. But if we talk about benefits, Angular has much to offer with webpack 5 and one of them is in terms of modularization using module federation. Webpack 5 is having an important feature of loading remote angular modules and stitching it with angular application at run time and that too without violating rules of zone.js. Its totally a game changer in javascript world. You can read more about it at Module Federation with Webpack 5. With this you can split your codebase with smaller bundle size and during runtime you can dynamically load them on demand, resulting in faster and independent deployments and maintainability. <br/> https://dzone.com/articles/howto-modularize-an-angular-application-by-example
| 65   | The role of Webpack in Angular <br><br> 
          https://javascript.plainenglish.io/role-of-webpack-in-angular-part-3-of-series-what-angular-is-5058d445e45c

          1. angular CLI uses a tool called webpack which is a build automation tool it gets all our scripts and stylesheets combines them outs them in a bundle and minifies that bundle and this is for optimization.
                    i) polyfills.bundle.js which includes all the scripts to fill the gap between the version of Javascript that Angular needs and the version of Javascript supported by most browsers.
                    ii)  main.bundle.js which includes all the source code of our application.
                    iii) styles.bundle.js which includes all our stylesheets. Here stylesheets are stored in a Javascript bundle.
                    iv) vendor.bundle.js which includes all the third-party libraries.          
          2. whenever we make changes in any of our file html, type-scripts or styles the webpack automatically recompile our application and refreshes our bundles. Go back to the browser and enter http://localhost:4200/ . The change in code will appear in browser without even refreshing the page — this is the feature of webpack called hot module replacement or hot module reloading so whenever the source file is modified webpack automatically refreshes our browser.
          3. we don’t have any references to our stylesheets or a script file in our code in index.html — the wepack automatically generate stylesheets & script files and integrate them in index.html dynamically at runtime. All the bundles that webpack generated it also injected them in index.html — everything happen dynamically at runtime.
          4. all our Styles are compiled into a Javascript bundle. And webpack is behind to automatically generate these bundles at compile time. It also injected them in index.html at runtime.
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 66   | What is Modularizing ? <br><br> Modularizing the application has helped the startup performance and shows how bigger downloads can be split. In this case, the initial load was more than halved. If the files are gzipped it is below 300 kb. <br/> TypeScript made it easy to split the code into ,odules. Splitting the templates was not as easy. The Angular compiler did not show the missing modules. The errors are shown at run time. It would be nice if Angular would have a feature that checks that all used modules are imported at compile time. <br/> Splitting an existing application into modules is quite easy and takes only a reasonable amount of effort. The better approach is to start the development of an application with modules, placing related components in modules with a common base route and subroutes to the components. The required imports can then be added during the development process. That keeps the startup performance okay, with little extra cost. <br> https://dzone.com/articles/howto-modularize-an-angular-application-by-example
| 67   | What is NgModule ? <br><br> Inside of the @NgModule operator, we define all the properties of the module. <br> Bootstrap ::=> Defines the root-component of the Application. Only use this in the AppModule. <br> Exports ::=> We define the components, directives or pipes we want to export here. <br> Declarations ::=> Inside of the declarations array, we define all the components, directives and pipes, that are declared and used inside this module. <br> Imports ::=> Your module can import as many sub-modules as you like. For example, if you want to use the HttpClient, you will need to import the HttpClientModule. <br> Providers ::=> We define any @Injectables, required by the module, here. Any sub-components or modules can then get the same instance of that @Injectable via dependency injection. In the case of the AppModule, these @Injectables are application-scoped.
| 68   | What is Angular CLI? <br><br>  Angular CLI, a command-line interface tool for Angular that you can use to initialize, build, scaffold, and prolong Angular applications directly from a command shell. Hence, we can say it is the official tool for initializing and operating with Angular projects. It helps you from out in the complex configurations and builds tools like TypeScript, Webpack, etc. <br> Although it uses Webpack to have all the packaging, importing, Browser Link, etc., you do not need to know how Webpack functions or how it needs to figure out to run in different environments or on other types of machines.
| 69   | What is Tree Shaking ? <br><br>  Tree shaking is a technique used to eliminate unused modules from the final bundle file of an application, reducing the download size and improving performance. The Angular CLI uses the Webpack bundler, which supports tree shaking from version 2. 
          Tree shaking refers to dead code elimination. It means that unused modules will not be included in the bundle during the build process.

          When we import and export modules in JavaScript, most of the time there is unused code floating around. Excluding that unused code (also referred as dead code) is called tree shaking.

          Utilizing the tree shaking and dead code elimination can significantly reduce the code size we have in our application. The less code we send over the wire the more performant the application will be.

![Tree Shaking Before](Tree_Shaking_before.png)
![Tree Shaking After](Tree_Shaking_after.png)
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 70   |  What is fixture? <br><br> A fixture is a wrapper for a component and its element & template. 
          const fixture = TestBed.createComponent(BannerComponent);
          TestBed.createComponent() creates an instance of the BannerComponent, adds a corresponding element to the test-runner DOM, and returns a ComponentFixture.
          
          it('should have <p> with "banner works!"', () => {
            const bannerElement: HTMLElement = fixture.nativeElement;
            const p = bannerElement.querySelector('p')!;
            expect(p.textContent).toEqual('banner works!');
          });
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 71   |  Web worker vs Service worker in angular ? <br><br> Web worker allows scripts to run in the background in separate threads to prevent scripts from blocking one another on the main thread. <br> Service workers are a proxy between the browser and the network. By intercepting requests made by the document, service workers can redirect requests to a cache, enabling offline access. 
| 72   |  How will write testcase for methods in angular ? <br><br> spyOn is used to mock the methods and get dummy return value using .and.returnValue(). You can use spyOn to check like that the particular method is called or not called.
| 73   |  What is the use of spyOn ? <br><br> 1. spyOn is used to mock the methods and get dummy return value using .and.returnValue() <br> 2. spyOn can call original function using .and.callThrough() <br><br> spyOn is used to mock external dependencies of the code being tested are replaced by dummy implementations so that the code to be tested can be controlled and test runs can be more quick and reliable.  All of the external dependencies like services, pipes, directives should be mocked to provide the expected level of isolation.
| 74   |   Third Party libraries in angular mostly used? <br><br> 1. ngx-logger (https://www.npmjs.com/package/ngx-logger) 2. trackjs (https://www.npmjs.com/package/trackjs) 
| 75   |   Root module vs Feature modules ? <br><br> Root module is simple a modules that can be bootstrapped as an application and render itself independently. Feature module is a module that contains related definitions but cannot render itself independently and must ultimately be loaded by a root module.
| 76   |   What Is Feature Modules in Angular? <br><br>So, in Angular Framework, Feature Module is simply an Angular module with module related kinds of stuff and purpose. But the main difference is that is not the root module of the application. Feature module is just an additional typescript based class with the @NgModule decorator and registered metadata. Feature modules isolate the applications based on the functionality or business operation and it collaborates with the root modules or any other feature modules. <br><br>The main purpose of the feature modules is to break down the functionality which focuses on any particular internal business operation or functionality that needs to be dedicated as a module so that we can achieve modularity in the application. With the help of feature modules, we also can restrict the responsibility of the root modules and help the root module to keep it thin and small.
| 77   |   Why Mocking is needed in Angular? <br><br> Mocking is a technique in unit testing in which the external dependencies of the code being tested are replaced by dummy implementations so that the code to be tested can be controlled and test runs can be more quick and reliable. In simple words, Mocking or Mock implementation is creating a dummy version of an external or internal service on which the code to be tested depends. Mocking in Jasmine Karma is generally replacing external dependencies with mock functions. <br><br> Whenever we encounter a dependency while unit testing, the standard practice is to mock or stub the dependency.
| 78   |  Difference between integration test and unit test? <br><br> 1. Integration test includes (“integrates”) the dependencies. Unit test replaces the dependencies with fakes in order to isolate the code under test. <br><br> 2. Unit test is written for individual units or components of an application. Integration tests is written for two or more units. An integration test does not test a complete workflow, nor does it test an isolated unit.
| 79   |  What is End-to-end testing ? <br><br>  In E2E testing, you test the workflow of your application from start to finish. In other words, you test for actions that real users can perform on your app to check that desired outputs are obtained.
Intercepting API calls to return fixed data

![Feature module](feature_module.png)

| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 80   |  How will test native element in angular ? <br><br> We can access HTML elements using fixture. It is used to get “DebugElement” for a DOM object. DebugElement is an Angular class that contains all kinds of references and methods relevant to investigate an element as well as component. nativeElement returns a reference to the DOM element which can also come under debugElement as stated above.<br>
            It works for querying both class something like (fixture.debugElement.nativeElement.querySelector('.shan')) as well as id.
            
            <div id="shan">Hey there</div>
            We can use below ways to get it in unit testing:

            ```
            fixture.debugElement.query(By.css('#shan'))
            fixture.debugElement.nativeElement.querySelector('#shan')
            document.getElementById('#shan')
            ```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 81   |  How will identify, diagnose and fix memory leaks in the application? <br><br> 
          In javascript, memory should be cleared up automatically using a thing called Garbage collector. Javascript is a language who ha garbage collector meaning you don't have to manage your memory manually. It gets cleared automatically & assigned automatically. 
          
          Symptons ::===> 1. Page unresponsive 2. browser simply gets slow and you cann't switch tab anymore 3. Your computer is become slow becuase your browser eats up more and more RAM of your computer 
          
          Reasons & Solutions of memory leaks ::===>  
          1. window.x = 10   it's a global variable. you probably heard many times is a realy bad practive to have global variables. 
            window.calc  = function() => {}  calc is a fuction and imagine it does something heavy inside. That's obviously gonna stay on the root becuase root is accessing it and garbage collectors think that is always active becuase it sits on the root. 
            First thing you can do use strict to prevent you from these memory leaks becuae it i going to throw errors as soon as you have global variables. Or simple not use any global variables. 
          2. When you have setTimeout or setInterval and you have a callback inside and have some dependencies. Dependencies are bad in timeout as long as you don't clear the timeout. 
          ```
          setTimeout(() => {
            let node = document.getElementById('demo');
          }, 1000);
          node.remove()
          ```
          let's imagine there is some node inside setTimeout function and usually when you delete node from your javascript. now i am removing the node using node.remove(). but this timeout always going to keep a reference to this even if it's deleted. 
          So make sure you are always clears timeout. To clear timeout, first assinging your timeout to some kind of a variable and quickly call clearTimeout() with variable inside it. In that way when timeout will be cleared, all references inside it also going to be garbage collected.   
        3.  make sure you delete it from object itself otherwise it's never going to get garbage collected.
        ```
        let nodes = {
           btn: document.getElementById('demo')
        }
        document.getElementById('demo').remove();
        ```
        you have to do the 
        delete nodes.btn
        
        Diagnose ::===> analyze Memory Leaks with Chrome DevTools: 
        1. Open DevTools 2. Go to the Memory panel 3.select the “Allocation instrumentation on timeline” radio button 4.Press the Start button
        1. open the Chrome Dev Tools 2. open the panel on the right 3. click on More Tools > Performance Monitor
        
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 82   |  What are Services in Angular? <br><br> Services helps us to share common business logic, data and functions with different components of an Angular application. They are implemented through dependency injection.
| 83   |  When should I use RxJS in Angular Application? <br><br> RxJS (Reactive Extensions for JavaScript) is a powerful library that allows developers to handle asynchronous data streams in a functional and efficient way. Angular heavily relies on RxJS for handling asynchronous operations, such as handling HTTP requests, event handling, and managing state changes. When working with Angular, you'll frequently use RxJS Observables to manage data streams, especially when interacting with APIs. In addition to its use in Angular development, RxJS is also a popular choice for reactive programming in other JavaScript frameworks and libraries, such as React, Vue. js, and Node.
| 84   | What is State Management? <br><br> State management refers to the process of managing the state of an application. The state is a representation of the data at a given point in time. In a typical Angular application, the state includes data such as user information, UI elements, and other application-specific data. Effective state management ensures that the state is consistent, predictable, and easy to debug. 
| 85   |  Give examples of State management libraries? <br><br> In Angular, two popular state management libraries are NgRx and Akita. Both libraries offer robust solutions for handling state in Angular applications, but they differ in their approaches and features.
| 86   |  Why needs NGRX in Angular? <br><br> NgRx is a reactive state management library for Angular applications. It will work as expected as all the components can get or set the required data from a specific service. But, the actual problem is if we refresh the page we will lose the application state stored in the angular service. <br/> It is based on the Redux pattern and leverages RxJS for reactive programming. NgRx provides a suite of libraries for managing state, side effects, entity collections, and more. NgRx is well-suited for large and complex applications where a strict and predictable state management pattern is needed. <br> <strong>Key Features of NgRx</strong> <br> 1) Redux Pattern: NgRx follows the Redux pattern, which is based on three core principles: a single source of truth, state is read-only, and changes are made using pure functions. <br> 2) Store: The store holds the application’s state and serves as the single source of truth. <br> 3) Actions: Actions are dispatched to indicate that something happened. <br> 4) Reducers: Reducers are pure functions that determine how the state changes in response to actions. <br> 5) Selectors: Selectors are pure functions used for obtaining slices of the state.
| 87   |  How you will test one service inside another service? To test a service, you set the providers metadata property with an array of the services that you'll test or mock. content_copy let service: ValueService; beforeEach(() => { TestBed. configureTestingModule({ providers: [ValueService] }); }); Then inject it inside a test by calling TestBed. 
| 88  |  Use of Rxjs <b>of</b> operator ? <br/> Ans. Writing unit testcase of injectable service in angular component. When we have a service for sucscribing inside a component, write spyOn with success & error response. Example : spyOn(dataService, 'makePost').and.returnValue(of(res)); spyOn(dataService, 'makePost').and.returnValue(throwError(() => error)); 
| 89   |  What is TestBed? <br><br> TestBed is the primary api for writing unit tests for Angular applications and libraries.
                    ```TestBed.configureTestingModule({
                          declarations: [LoginComponent],
                          providers: [AuthService]
                       });
                       // create component and test fixture
                        fixture = TestBed.createComponent(LoginComponent); (2)

                        // get test component from the fixture
                        component = fixture.componentInstance; (3)

                        // UserService provided to the TestBed
                        authService = TestBed.get(AuthService); (4)
                        
          i) A fixture is a wrapper for a component and its template.
          ii) We create an instance of a component fixture through the TestBed, this injects the AuthService into the component constructor.
          iii) We can find the actual component from the componentInstance on the fixture.
          iv) We can get resolve dependencies using the TestBed injector by using the get function.
          ```
| No. | Questions                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 90   |  Where NGRX or Redux stores state data ? <br/><br/> The store doesn't local/session storage, but all of the entities are stored in memory. A Redux/NGRX state is stored in RAM (internal memory) for all data, do not use Cookies or LocalStorage. The redux store is just a JavaScript object so as long as the machine has enough memory it won't run out.
| 91   |  How would you efficiently handle 5000 records from an API call for a dropdown? <br/><br/> https://medium.com/geekculture/simple-way-to-load-small-chunks-of-data-as-you-scroll-in-angular-6a14ec498989 https://medium.com/coding-in-depth/angular-binding-dropdown-with-huge-data-set-af2ef245e548 https://blog.bitsrc.io/3-ways-to-render-large-lists-in-angular-9f4dcb9b65 https://dev.to/pragativerma18/unlocking-the-power-of-api-pagination-best-practices-and-strategies-4b49 
| 92   |  NGXS vs NGRX? <br/><br/>In NGXS, the application state is stored in a Store, which is defined as a class. The Store class contains properties that represent different sections or nodes of the application state. These properties are initialized at the start of the application and can be modified by actions to update the state. The NgRx library requires us to create a separate reducer. NGXS doesn't have any reducer. <br/> https://danielszpisjak.com/blog/ngxs-vs-ngrx-a-comprehensive-guide-to-state-management-in-angular/
| 93   |  Third party package for taking Screenshot or generating PDF? <br/><br/> html2canvas - take "screenshots" of webpages <br/> jspdf - PDF Document creation from JavaScript
| 94   |  Third party package for table with CRUD operations? <br/><br/> AG Grid - AG Grid is a feature-rich Data Grid for all major JavaScript frameworks, offering filtering, grouping, pivoting, and more. Free and open-source.
| 95   |  What is Nx Monorepo? <br/><br/> Nx monorepo is a development approach where multiple interrelated projects are stored in a single repository, allowing the team of developers to share code and collaborate more seamlessly. It's prevalent in large-scale projects with many independent components. <br/> Imagine you have a collection of distinct but interrelated projects. For instance, you might have an app with its own React frontend and Node.js backend, or two different Angular applications sharing a common collection of components. Monorepos offer an effective solution to organize these distinct but interrelated projects into a single repository. <br/> With a monorepo, all related projects can be housed in a single location, providing clear visibility over all your projects. When you make new changes to one project, you can easily assess how it impacts the others. <br/> Monorepos facilitate seamless code sharing, collaborative work on projects, and synchronization of releases across different projects. However, managing multiple interdependent projects within a single repository requires a capable build tool, such as Nx, to efficiently handle the intricacies.
| 96   |  What's Monorepo? <br/><br/> In traditional development workflows, each project has its own repository. This approach can lead to many problems, such as duplication of code, inconsistent dependencies, and poor communication between teams. Monorepo addresses these problems by storing all the projects in a single repository. This approach can make it easier to manage and scale a large codebase, as it allows for better organization, collaboration, and reuse of code. Overall, Monorepos consists of a single repository with multiple projects (think of it as a single big folder containing the entire codebase). <br/> Monorepos became very popular when Google exposed that they were using a single repository for both Gmail and YouTube. In fact, Google uses the monorepo paradigm to organize their code structure. Other companies like Facebook, Twitter, Uber, Netflix, etc. also use monorepos. <br/><br/> Pros : 1) Easier code sharing <br/> 2) Better collaboration between teams <br/> 3) Easier to maintain external packages/dependencies <br/> 4) Single store for code styles, formatting and linting across solutions <br/> 5) Test can be run across platform when a change is made to a shared service/feature/package. <br/><br/> Cons : 1) More complex for smaller projects <br/> 2) Longer build times (possible) <br/> 3) Repository Size <br/> 4) Managing dependency <br/> 5) Restricting access to apps/libs for certain teams/outsourcers. <br/><br/> <strong>There are several tools available to help manage Monorepos, including:</strong><br/> 1) NX 2) Lerna 3) Yarn Workspaces <br/><br/> https://medium.com/@magenta2127/monorepo-vs-multi-repo-vs-monolith-7c4a5f476009
| 97   |  What is Nx ? <br/><br/> NX is a set of powerful tools and best practices for building and maintaining complex applications. NX provides a number of benefits: <br/><br/> 1) A set of powerful command-line tools: NX provides a set of powerful command-line tools for building, testing, and deploying your applications. <br/> 2) A set of best practices: NX provides a set of best practices for developing applications in a Monorepo. These best practices help you to write better code, faster. <br/> 3)An extensible plugin system: NX provides an extensible plugin system that allows you to add new features and capabilities to your applications. <br/> https://dev.to/thekrprince/getting-started-with-monorepo-using-nx-17j0
| 98   |  Is a monorepo a monolith ? <br/><br/> A monolith is an app with related data to this app. While a monorepo may contain a monolith, a monolith is not always in a monorepo. A monolith can be broken up into microservices, but a monorepo can only be broken down into individual repositories. Monorepos are sometimes referred to as monolithic repositories. However, monolithic architecture, used for building self-contained applications, should not be confused with monorepos. Also, It is important to note that monorepos are the exact opposite of multirepos. Monorepos consists of a single repository with multiple projects (think of it as a single big folder containing the entire codebase), while multirepos consists of different projects, with each having its own repository.
| 99   |  Monorepo vs MicroFrontend ? <br/><br/> A monolith is an app with related data to this app. While a monorepo may contain a monolith, a monolith is not always in a monorepo. <br/> A monolith can be broken up into microservices, but a monorepo can only be broken down into individual repositories. <br/> The opposite of a monorepo is a multirepo (or a polyrepo) and the opposite of a monolith is distributed microservices. <br/> Monoliths have tightly coupled code bases which can only be decoupled by distributed microservices not by polyrepos or monorepos. <br/> A monorepo is often mistakenly thought to be a monolith - this is when code is colocated with no clear establishment of the relationship or use of such a stratgey. <br/> And a monolith is often broken down into polyrepos each with their own code base to decouple code. This decoupling of code is best when related code bases are still colocated without being tightly coupled. <br/> Monorepos can solve some of the challenges faced by a polyrepo approach - inconsistent tooling, duplication of code, a lack of ease in code sharing. <br/> A combination of monorepos and microservices could solve the challenges of monorepos as monorepos are expensive in terms of data storage. Microservices for the distribution of these data sets across microservices may be one available solution. <br/> A monolith may have different package managers, different stacks and different sets of data configured in different ways all related to a single application. <br/><br/> https://monorepo.tools/
| 100   |  npm ci vs npm i ? <br/><br/> <strong>npm ci</strong> - install exactly what is listed in package-lock.json. keep in mind the package-lock.json file is going to be tied to the specific version of Node that originally created it. all the packages it downloads are going to be for that Node version, even if your Node version is different. <br/> <strong>npm install</strong> - without changing any versions in package.json, use package.json to write package-lock.json, then install exactly what is listed in package-lock.json
| 101   |  Does Angular build use webpack? <br/><br/> Webpack is a popular module bundler, a tool for bundling application source code in convenient chunks and for loading that code from a server into a browser. The Angular build process uses webpack behind the scenes to transpile TypeScript to JavaScript, transform Sass files to CSS, and many other tasks. To understand the importance of this build tool, it helps to understand why it exists. <br/> https://developer.okta.com/blog/2019/12/09/angular-webpack#:~:text=The%20Angular%20build%20process%20uses,limited%20support%20for%20JavaScript%20modules.
| 102   |  Extends vs Implements ? <br/><br/> extends: You get all these methods/properties from the parent class so you don't have to implement this yourself. <br/> implements: It is a contract that the class has to follow. The class has to implement at least the following methods/properties.
```
class Person {
  name: string;
  age: number;
  walk(): void {
    console.log('Walking (person Class)')
  }
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}

class child extends Person { }

class man implements Person {
  name: string;
  age: number;
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
  walk(): void {
    console.log('Walking (man class)')
  }
}

(new child('Mike', 12)).walk();
// logs: Walking(person Class)

```

