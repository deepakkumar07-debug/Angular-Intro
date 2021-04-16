# Angular-Intro

## Installing Angular CLI
https://angular.io/cli

    npm install -g @angular/cli


    ng new my-first-project
    cd my-first-project
    ng serve

## Workspaces and project files

- The `ng new` command creates an Angular workspace folder and generates a new app skeleton. 

https://angular.io/guide/file-structure
https://angular.io/guide/glossary#workspace
https://angular.io/guide/workspace-config

when we do ng serve
it generate bundles for javascript and css files
main.bundle.js
styles.bundle.js

## file structure
1. e2e
    where we write our end-to-end tests for our application which means thease are basically automated tests simulate a real user we can write code to launch our browser navigate to home page of our application

    - click a few links here and there fill out a form click a button
    - and assert that there is something on the page

2. node modules
    this is where we store all the third party that our application may be depended upon this folder is purely for development
    - so when we compiler our application parts of these are put in bundle and depl;oyed with our application
    - we're not going to deploy this node modules to the server

3. src
    - src stands for source this is where we have a actual source code of our application inside we have

    - `app` folder inside this folder we have  module and a component
    names with modules are module component are component

    - every application has atleast one module and one component

    - `src\app\assets` below that we have assets folder this is where we store all static assets of our application
    examples images,icons..
    - `src\app\environments` below that we have environments folder this is where we store configureation settings for different environments
    
    * one for production environment  =>`environment.prod.ts`
    * other for development environment =>`environment.ts`

    - other files in src folder are `favicon.ico` which is displayed in the browser
    - and we have index.html
            note here in `index.html` we dont have scripts or style references these references will be dynamically inserted into this page

    - we have `main.ts` which is a typescript file this is basically a starting point of our application here we are bootstarpping our main module which is APPModule
    unlike other programming language we have this main method
    - we have `polyfill.ts` which basically imports some scripts which are required for running angular because the angular framework uses feautures of javascript that are not available of current version of javascript supported by most browser out there so these polyfills fill the gap between feautures of javascript and angular needs and the feautures supported by the current browsers.
    - we have `styles.css` which is a global styles for our application and also each page or each component as it own styles
    - we have `test.ts` which is basically used for setting up of testing environment.

now outside of src folder

4. `angular-cli.json` project-specific configuration defaults for build and development tools provided by the Angular CLI
 when we do ng new projectName => this command will create folder with all required components. and this file denotes how our project folder structure should be where to begin all configuartion are writtten in this file as json format.

5. `.editorconfig` we have this file if we working on a team all developers in the team use the same settings in thier editors this where we store settings

6. `.gitignore` for excluding certain files and folders from git repository (right now just ignore )

7.  `karma.conf.js`
        which is a configuration for karma which is a test runner for javascript code we dont worry about that until we run any testcases

8. `package.json` important file
    this is a standard file that every node project has inside this file we have "dependencies": which determines libraries that our application is dependent upon

    all libraries are start with @angular/libraryName if we not use any of these we can delete it

    and another one is devDependencies these libraries purely for development machine we dont need this for production server 

    karma is a test runner


9. `tsconfig.json`
        bunch of settings for our typescript compiler so your typescript compiler looks at these settings based on these settings is going to compile our typescript code into javascript that browsers can understand
            **"target":"es2015"**
        - in future we want change our typescript compiler this whewre we change

10. `tslint.json`
    number of settings for tslint. tslint is a static analysis tool for typeScript code. it checks our typescript code for readability maintainability and functionality errors


11.  The difference is that `tsconfig.app.json `is a file that is related to the Angular App in particular, while `tsconfig.json `is a more general file that contains general typescript configuration. It's especially useful when you have a micro frontends system, where there are multiple Angular subprojects, each of them with its own tsconfig.app.json configuration. But if you want you could perfectly merge these two files into one, actually you surely noticed that tsconfig.app.json contains the line:


            "extends": "./tsconfig.json"

which means that the whole App uses the configuration stated in tsconfig.app.json plus the configuration in tsconfig.json

    https://stackoverflow.com/questions/54898013/difference-between-tsconfig-json-and-tsconfig-app-json-files-in-angular

12. `tsconfig.spec`

    It is TypeScript configuration for the application tests.

    For example below code you says

        "types": ["jasmine", "node"]
        
I will use jasmine for testing on nodejs environment.

