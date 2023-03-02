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
| 58   |  Why need Lazy loading ?
| 59   |  How can you share data between components?
| 60   |  What is Two way data binding?
| 61   |  Is constructor a part of angular ?
| 62   |  What is Dependency Injection? <br><br> 1. Using Dependency Injection we move the creation of binding dependent object otside of the class that depend on them. 2. DI keeps the code more flexible testable and mutable. 3. Class can inherit external logic without having to create on its own. 4. DI benefits directives, pipes and components.  <br><br> Consider all the components of an application performing common tasks like accessing database, rendering images on the view etc. To avoid rewriting of code, angular services can be used. These services can then be injected into the components that require that service. 
| 63   |  What is Webpack? <br><br> Webpack is a module bundler that lets you compile JavaScript modules (Files, Images, Fonts, JS, CSS, HTML, etc.). Webpack offers multiple functions, like merging modules, code minimization (or minimizing code by eliminating spaces, remarks, junk code, and code reduction), SASS or TypeScript compiling, integration with npm, and other features.
```
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
```
| 63   |  Is Webpack needed for Angular? <br><br> While the primary purpose of Webpack is to build multiple modules into a single file, it is not bound to only bundling source files. <br> Usually, webpack is hidden behind the Angular command-line tool. But in some cases, it may be necessary to tweak the configuration of webpack when building an Angular application. In earlier versions of Angular, it was possible to eject the webpack configuration and modify it directly.
| 64   | What benefits does Webpack 5 bring to Angular 12? <br><br> I understand the build time is increased for you with webpack 5. But if we talk about benefits, Angular has much to offer with webpack 5 and one of them is in terms of modularization using module federation. Webpack 5 is having an important feature of loading remote angular modules and stitching it with angular application at run time and that too without violating rules of zone.js. Its totally a game changer in javascript world. You can read more about it at Module Federation with Webpack 5. With this you can split your codebase with smaller bundle size and during runtime you can dynamically load them on demand, resulting in faster and independent deployments and maintainability. <br/> https://dzone.com/articles/howto-modularize-an-angular-application-by-example
| 65   | The role of Webpack in Angular <br><br> 
```
https://javascript.plainenglish.io/role-of-webpack-in-angular-part-3-of-series-what-angular-is-5058d445e45c

1. angular CLI uses a tool called webpack which is a build automation tool it gets all our scripts and stylesheets combines them outs them in a bundle and minifies that bundle and this is for optimization.
          i) polyfills.bundle.js which includes all the scripts to fill the gap between the version of Javascript that Angular needs and the version of Javascript supported by most browsers.
          ii)  main.bundle.js which includes all the source code of our application.
          iii) styles.bundle.js which includes all our stylesheets. Here stylesheets are stored in a Javascript bundle.
          iv) vendor.bundle.js which includes all the third-party libraries.          
2. whenever we make changes in any of our file html, type-scripts or styles the webpack automatically recompile our application and refreshes our bundles. Go back to the browser and enter http://localhost:4200/ . The change in code will appear in browser without even refreshing the page — this is the feature of webpack called hot module replacement or hot module reloading so whenever the source file is modified webpack automatically refreshes our browser.
3. we don’t have any references to our stylesheets or a script file in our code in index.html — the wepack automatically generate stylesheets & script files and integrate them in index.html dynamically at runtime. All the bundles that webpack generated it also injected them in index.html — everything happen dynamically at runtime.
4. all our Styles are compiled into a Javascript bundle. And webpack is behind to automatically generate these bundles at compile time. It also injected them in index.html at runtime.

```
| 66   | What is Modularizing ? <br><br> Modularizing the application has helped the startup performance and shows how bigger downloads can be split. In this case, the initial load was more than halved. If the files are gzipped it is below 300 kb. <br/> TypeScript made it easy to split the code into ,odules. Splitting the templates was not as easy. The Angular compiler did not show the missing modules. The errors are shown at run time. It would be nice if Angular would have a feature that checks that all used modules are imported at compile time. <br/> Splitting an existing application into modules is quite easy and takes only a reasonable amount of effort. The better approach is to start the development of an application with modules, placing related components in modules with a common base route and subroutes to the components. The required imports can then be added during the development process. That keeps the startup performance okay, with little extra cost. <br> https://dzone.com/articles/howto-modularize-an-angular-application-by-example
| 67   | What is NgModule ? <br><br> Inside of the @NgModule operator, we define all the properties of the module. <br> Bootstrap ::=> Defines the root-component of the Application. Only use this in the AppModule. <br> Exports ::=> We define the components, directives or pipes we want to export here. <br> Declarations ::=> Inside of the declarations array, we define all the components, directives and pipes, that are declared and used inside this module. <br> Imports ::=> Your module can import as many sub-modules as you like. For example, if you want to use the HttpClient, you will need to import the HttpClientModule. <br> Providers ::=> We define any @Injectables, required by the module, here. Any sub-components or modules can then get the same instance of that @Injectable via dependency injection. In the case of the AppModule, these @Injectables are application-scoped.
| 68   | What is Angular CLI? <br><br>  Angular CLI, a command-line interface tool for Angular that you can use to initialize, build, scaffold, and prolong Angular applications directly from a command shell. Hence, we can say it is the official tool for initializing and operating with Angular projects. It helps you from out in the complex configurations and builds tools like TypeScript, Webpack, etc. <br> Although it uses Webpack to have all the packaging, importing, Browser Link, etc., you do not need to know how Webpack functions or how it needs to figure out to run in different environments or on other types of machines.
| 69   | What is Tree Shaking ? <br><br>  Tree shaking is a technique used to eliminate unused modules from the final bundle file of an application, reducing the download size and improving performance. The Angular CLI uses the Webpack bundler, which supports tree shaking from version 2. 
```
Tree shaking refers to dead code elimination. It means that unused modules will not be included in the bundle during the build process.

When we import and export modules in JavaScript, most of the time there is unused code floating around. Excluding that unused code (also referred as dead code) is called tree shaking.

Utilizing the tree shaking and dead code elimination can significantly reduce the code size we have in our application. The less code we send over the wire the more performant the application will be.

![Tree Shaking Before](Tree_Shaking_before.png)
![Tree Shaking After](Tree_Shaking_after.png)

```
