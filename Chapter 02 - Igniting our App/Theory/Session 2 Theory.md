## Namaste React Course by Akshay Saini
# _Chapter 02 - Igniting our App_


## Q: What is `NPM`?
A: It is a tool used for package management (It manage all the packages that we install in system these packages are also known as dependancy) and the default package manager for Node projects. `NPM is installed when NodeJS` is installed on a machine. It comes with a command-line interface (CLI) used to interact with the online database of NPM. This database is called the NPM Registry, and it hosts public and private 'packages.' To add or update packages, we use the NPM CLI to interact with this database. 
- `npm` alternative is `yarn`

### How to initialize `npm`?
```
npm init
```
`npm init -y` can be used to skip the setup step, `npm` takes care of it and creates the `package.json` json file automatically , but without configurations.

### What is `bundler`?
A: A bundler is a development tool that combines many JavaScript code files into a single one that is production-ready loadable in the browser. in our project we usually have html, css, js etc files so for making this production-ready our whole code needs to be bundle, compressed, minified and bundler helps us to do the same. the job of bundler is to bundle/package your app properly so that it can be shif to production.

## Q: What is `Parcel/Webpack`? Why do we need it?
A: `Parcel/Webpack` is type of a web application bundler used for development and productions purposes or power our application with different type functionalities and features.
It offers blazing fast performance utilizing multicore processing, and requires zero configuration. Parcel can take any type of file as an entry point, but an HTML or JavaScript file is a good place to start.
Parcel/Webpack are type of bundlers that we use to power our application with different type functionalities and features.

### Parcel Features: - https://parceljs.org/ 
* DEV and production Build
* It creates a local server
* HMR (Hot Module Replacement) - parcel keeps track of file changes via `file watcher algorithm` and renders the changes in the files
* `File watcher algorithm` - this algorithm made with C++
* Super fast building algorithm
* Parcel gives faster development experience (faster builds) because of caching - when we run parcel it creates parcel-cache folder that do caching everything we do.
* Image optimization
* Minification
* Compresses
* Cleaning our code
* Bundling
* Differential Bundling - support older browser (parcel give the ability to have different bundles for different types of older browsers) that means Compatible with older version of browser
* Diagnostic - give error display screen
* HTTPS in dev
* Port Number
* Consistent hashing algorithm
* Zero Configuration
* Automatic code splitting
* Tree shaking - remove unused code
* Different dev and prod bundlers

### installation commands:
- Install:
```
npm install -D parcel
```
`-D` is used for development and as a development dependency.

- Parcel Commands :
    - For development build:
    ```
    npx parcel <entry_point> 
    ```
    - For production build :
    ```
    npx parcel build <entry_point> 
    ```

## Q: What is `.parcel-cache`?
A: `.parcel-cache` is used by parcel(bundler) to reduce the building time.
It stores information about your project when parcel builds it, so that when it rebuilds, it doesn't have to re-parse and re-analyze everything from scratch. It's a key reason why parcel can be so fast in development mode.


## Q: What is `npx`?
A: `npx` is a tool that is used to execute the packages. It comes with the npm, when you installed npm above 5.2.0 version then automatically npx will installed. It is an npm package runner that can execute any package that you want from the npm registry without even installing that package.


## Q: What is difference between `dependencies` vs `devDependencies`?
A: `Dependencies` should contain library and framework in which your app is built on, needs to function effectively. such as Vue, React, Angular, Express, JQuery and etc. (It will use in production)
`DevDependencies` should contain modules/packages a developer needs during development. (Only require during development phase)
such as, `parcel, webpack, vite, mocha`.
`These packages` are `necessary only while you are developing your project`, not necessary on production.
To save a dependency as a devDependency on installation we need to do, 
```
npm install --save-dev
```
instead of just,
```
npm install --save
```
## Q: Difference between tilde ( ~ ) and caret ( ^ ) in package.json
A: https://www.geeksforgeeks.org/difference-between-tilde-and-caret-in-package-json/

## Q: What is `Tree Shaking`?
A: `Tree shaking` is process of removing the unwanted code that we do not use while developing the application.
In computing, tree shaking is a dead code elimination technique that is applied when optimizing code.


## Q: What is `Hot Module Replacement`?
A: `Hot Module Replacement (HMR)` exchanges, adds, or removes modules while an application is running, without a full reload. This can significantly speed up development in a few ways: Retain application state which is lost during a full reload.


## Q: List down your favorite `5 superpowers of Parcel` and describe any 3 of them in your own words.
A: `5 superpowers of Parcel`:
* `HMR (Hot Module Replacement)` - adds, or removes modules while an application is running, without a full reload.
* `File watcher algorithm` - File Watchers monitor directories on the file system and perform specific actions when desired files appear.
* `Minification` - Minification is the process of minimizing code and markup in your web pages and script files.
* `Image optimization`
* `Caching while development`


## Q: What is `.gitignore`? What should we `add and not add` into it?
A: The `.gitignore file` is a text file that tells `Git` which files or folders to `ignore` in a project during `commit to the repository`.
The types of files you should consider adding to a .gitignore file are any files that do not need to get committed. for example, For security, the security key files and API keys should get added to the gitignore.
`package-lock.json` should `not add` into your `.gitignore` file.

The entries in this file can also follow a matching pattern.
```
* is used as a wildcard match
/ is used to ignore pathnames relative to the .gitignore file
# is used to add comments to a .gitignore file
```
This is an example of what the .gitignore file could look like:
```
# Ignore Mac system files
.DS_store

# Ignore node_modules folder
node_modules

# Ignore all text files
*.txt

# Ignore files related to API keys
.env

# Ignore SASS config files
.sass-cache
```


## Q: What is the difference between `package.json` and `package-lock.json`?
A: 
* https://www.geeksforgeeks.org/difference-between-package-json-and-package-lock-json-files/#:~:text=this%20problem%2C%20package.-,lock.,same%20dependencies%20as%20in%20package.
* https://www.notion.so/package-json-vs-package-lock-json-664ec8b02bac47468960368a7842a308?pvs=4 

`package.json`:
* This file is mandatory for every project
* It contains basic information about the project
* Application name/version/scripts
* package.json is a configuration for npm

`package-lock.json`:
* This file is automatically generated for those operations where npm modifies either the node_module tree or package-json.
* It is generated after an npm install
* It allows future devs & automated systems to download the same dependencies as the project.
* it also allows to go back to the past version of the dependencies without actual
‘committing the node_modules folder.
* It records the same version of the installed packages which allows to reinstall them.
Future installs will be capable of building identical description tree.

**~** or **^** in `package.json` file :
These are used with the versions of the package installed.

For example  in `package.json` file:
```
"dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  }
```

* **~** : `Approximately equivalent to version`, will update you to all future patch versions, without incrementing the minor version.
* **^** : `Compatible with version`, will update you to all future minor/patch versions, without incrementing the major version.

> If none of them is present, that means only the version specified in `package.json` file is used in the development.

## Q: Is it a good idea to push `package.json and package-lock.json` on git?
A: Yes, both file maintains a note of what all dependencies our project needs. for example package.json maintaining that our code needs Parcel as dependency and package-lock.json maintaining the all the versions of the dependencies. `that's why package-lock.json is huge it's basically maintaining the exact version of each dependencies.`

## Q: Why should I not modify `package-lock.json`?
A: `package-lock.json` file contains the information about the dependencies and their versions used in the project. Deleting it would cause dependencies issues in the production environment. So don't modify it, It's being handled automatically by NPM.

## Q: What is `node_modules` ? Is it a good idea to push that on git?
A: `node_modules` folder like a cache for the external modules that your project depends upon. When you npm install them, they are downloaded from the web and copied into the node_modules folder and Nodejs is trained to look for them there when you import them (without a specific path).
"Node_module is like a database it contains the actual data of the dependencies, node_module is very heavy as it contains transitive dependency of the dependencies (that means dependencies of dependency) so node_modules is like a collection of dependencies"
`Don't push node_modules`in github because it contains lots of files(more than 100 MB), it will cost you memory space. `also if you have package.json and package-lock.json we can regenerate node_modules and this can be done by running npm install (and it will re-create node_modules)`

## Q: What is the `dist` folder?
A: The `/dist` folder contains the minimized version of the source code. The code present in the `/dist` folder is actually the code which is used on production web applications. Along with the minified code, the /dist folder also comprises of all the compiled modules that may or may not be used with other systems.


## Q: What is `browserslist`? https://browserslist.dev/?q=bGFzdCAyIHZlcnNpb25z 
A: `Browserslist` is a npm package is a tool that allows specifying which browsers should be supported in your frontend app by specifying "queries" in a config file (package.json). It's used by frameworks/libraries such as React, Angular and Vue, but it's not limited to them.

## Q: What are the ways to bring react into your project?
A: There could be multiple ways to do this
* By using CDN links (Though this is not a good way to do because - 1. It's costly operation 2. if the new version comes out we will need to change CDN links)
* By using npm

## Q why we write type=module in <script>?
A: We get error called `Browser scripts cannot have imports or exports.` that's why we write type=module that is `<script type="module" src="./App.js"></script>`modules support special keywords and features, we must tell the browser that a script should be treated as a module, by using the attribute <script type="module"> . The browser automatically fetches and evaluates the imported module (and its imports if needed), and then runs the script.

## Q Why we get `ReferenceError: React is not defined` error in js files?
A: We must import react and react-dom in the js files

## Q Why we remove "main": "App.js" from package.json files while running parcel for prod mode?
A: main in the package.json files is the way to show entry point of our project but when we run `npx parcel build index.html` we already given entry point of the project that's why we remove "main": "App.js" from package.json files.

