## Namaste React Course by Akshay Saini
# Chapter 03 - Laying the Foundation

## Q: What is `JSX`?
A: 
- JSX stands for JavaScript XML.
- JSX allows us to write HTML elements in JavaScript and place them in the DOM without any React.createElement() and/or appendChild() methods.
- JSX makes it easier to write and add HTML in React.
- JSX converts HTML tags into react elements.
- JSX is not HTML in JS. you can say - It's HTML-like or XML-like syntax.
- If we want to give attribute to JSX we have to use camelCase
- In normal HTMl we write class="test" but in JSX we write className="test"
- JSX prevent Cross Site Scripting attack for us.


### Example 1 using JSX:
```
const myElement = <h1>I Love JSX!</h1>;
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```
### Example 2 Without JSX:
```
const myElement = React.createElement('h1', {}, 'I do not use JSX!');
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```


## Q: Superpowers of `JSX`.
A: Using JSX, you can write markup inside Javascript, providing you with a superpower to write logic and markup of a component inside a single .jsx file. JSX is easy to maintain and debug.
### Example
```
function greeting(user) {
//JSX
  return <h1>{user}, How are you!!!</h1>;
}
```


## Q: Role of `type` attribute in script tag? What options can I use there?
A: The `type` attribute specifies the type of the script. The type attribute identifies the content between the `<script>` and `</script>` tags. It has a Default value which is “text/javascript”.
### `type` attribute can be of the following types:
- `text/javascript` : It is the basic standard of writing javascript code inside the `<script>` tag.
    ### Syntax
    ```
    <script type="text/javascript"></script>
    ```
- `text/ecmascript` : this value indicates that the script is following the `EcmaScript` standards.
- `module`: This value tells the browser that the script is a module that can import or export other files or modules inside it.
- `text/babel` : This value indicates that the script is a babel type and required bable to transpile it.
- `text/typescript`: As the name suggest the script is written in `TypeScript`.

## Q: `{TitleComponent}` vs `{<TitleComponent/>}` vs `{<TitleComponent></TitleComponent>}` in `JSX`.
A: The Difference is stated below:
- `{TitleComponent}`: This value describes the `TitleComponent` as a javascript expression or a variable. 
The `{}` can embed a javascript expression or a variable inside it.
- `<TitleComponent/>` : This value represents a Component that is basically returning Some JSX value. In simple terms `TitleComponent` a function that is returning a JSX value.
A component is written inside the `{<  />}` expression.
- `<TitleComponent></TitleComponent>` :  `<TitleComponent />` and `<TitleComponent></TitleComponent>` are equivalent only when `< TitleComponent />` has no child components. The opening and closing tags are created to include the child components.
### Example
```
<TitleComponent>
    <FirstChildComponent />
    <SecondChildComponent />
    <ThirdChildComponent />
</TitleComponent>
```

## Q: How to make shortcut for the script we write to run the project?
A: We add command in `scripts` inside package.json 
eg: we write `npx parcel index.html` to run the project in development mode. instead of writing this we can create a script/shortcut.

"scripts": {
  "start": "parcel index.html",
  "build": "parcel build index.html"
}

And then we can use it like: `npm run start` also instead of this we can also write `npm start` to run the project. hence `npm run start` === `npm start`. but we can't use prod build script without run eg `npm run build` !== `npm build`

Note:- React.createElement is => ReactElement => JS Object => that becomes HTML element while rendering.

## Q: Is browser understands JSX?
A: Browser doesn't understand JSX, the JSX code is transpiled before it reachs the JS engine. transpilation is done by PARCEL and the parcel doesn't do it by itself it's done by Bable. when we install Parcel, the parcel also install babel as it's dependencies.

JSX (Bable transpiled before it reachs the JS engine) => parcel => Babel

JSX => Bable transpiled it to React.createElement => ReactElement wihch is eventually => JS Object => HTML element (render)

## Q: What is functional component?
A: This is normal js functions that returns a pice of JSX. The component name always starts with a capital letter.

## Q: What is component composition?
A: When we composite 2 components one in another. or calling one component in another component.
