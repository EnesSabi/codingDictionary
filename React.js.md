# React.js
## What is React?
React, sometimes referred to as a frontend JavaScript framework, is a JavaScript library created by META.
React is a tool for building UI components. React creates a VIRTUAL DOM in memory.
Instead of manipulating the browser's DOM directly, React creates a virtual DOM in memory, where it does all the necessary manipulating, before making the changes in the browser DOM.
React only changes what needs to be changed!
## Getting Started
To use React in production, you need npm which is included with Node.js. To get an overview of what React is, you can write React code directly in HTML. But in order to use React in production, you need npm and Node.js installed.
Start by including three scripts, the first two let us write React code in our JavaScripts, and the third, Babel, allows us to write JSX syntax and ES6 in older browsers.
```html
    <script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
```
This way of using React can be OK for testing purposes, but for production you will need to set up a React environment
## Setting up the React Environment
If you have npx and Node.js installed, you can create a React application by using ```create-react-app```.
Run this command to create a React application named my-react-app: ```npx create-react-app my-react-app```
The create-react-app will set up everything you need to run a React application.
Run this command to move to the my-react-app directory and start the application:
```shell
cd my-react-app
npm start
```
The Standard React App is normally at localhost:3000. The Standard folder for the code of the website is at myReactApp/src/App.js. If the file is changed and saved the website immediately refreshes the chenged objects.
If you are more experienced then get rid of unnecessary code and files.
## Upgrade React
If your React Version is outdated, then you need to updated it. Install the latest version with ```npm i react@latest react-dom@latest```
### React 18
```javascript
// Before
import ReactDOM from 'react-dom';
ReactDOM.render(<App />, document.getElementById('root'));

// After
import ReactDOM from 'react-dom/client';
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```
### React 17
You're application will work without using the new root API. If you continue to use ReactDOM.render your application will behave like React 17.
## ES6
React uses ES6, and you should be familiar with some of the new features like:
1. Classes
2. Arrow Functions
3. Variables (let, const, var)
4. Array Methods like .map()
5. Destructuring
6. Modules
7. Ternary Operator
8. Spread Operator
This is plain JavaScript, so if you didn't learn JS, do it before you continue.

### Classes
A class is a type of function, but instead of using the keyword function to initiate it, we use the keyword class, and the properties are assigned inside a constructor() method.
```javascript
class Car { //Blueprint of an object
    constructor(name) {
        this.brand = name;
    }
    present() {
        return "I have a " + this.brand;
    }
}
class Model extends Car { //
    constructor(name, mod) {
        super(name); //super constructor to inherit the constructor of car
        this.model = mod
    }
    show() {
        return this.present() + ", it is a " + this.model;
    }
}
const myCar = new Car("VW");
const myCar2 = new Model("Ford", "Fiesta");// Objects
myCar.present(); //Methods
myCar2.show();
```
The class name should be uppercase as the coding convention dictates.
### Arrow Functions
Arrow functions allow us to write shorter function syntax:
```javascript
//normal declaration
hello = function() {
    return "Hello World!";
}
// or faster declaration with arrow
hello = () => {
    return "Hello World!";
}
// or shorter than that
// This works only if the function has only one statement.
hello = () => "Hello World!";
hello = (val) => "Hello " + val;
// and the shorter version
hello = val => "Hello " + val;
```
#### ```this``` with arrows
With arrow functions there is no binding of this.
With a regular function, this represents the object that called the function:
```javascript
class Header {
  constructor() {
    this.color = "Red";
  }
//Regular function:
  changeColor = function() {
    document.getElementById("demo").innerHTML += this;
  }
}
const myheader = new Header();
//The window object calls the function:
window.addEventListener("load", myheader.changeColor);
//A button object calls the function:
document.getElementById("btn").addEventListener("click", myheader.changeColor);
```
With an arrow function, this represents the Header object no matter who called the function:
```javascript
class Header {
  constructor() {
    this.color = "Red";
  }
//Arrow function:
  changeColor = () => {
    document.getElementById("demo").innerHTML += this;
  }
}
const myheader = new Header();
//The window object calls the function:
window.addEventListener("load", myheader.changeColor);
//A button object calls the function:
document.getElementById("btn").addEventListener("click", myheader.changeColor);
```
Remember these differences when you are working with functions. Sometimes the behavior of regular functions is what you want, if not, use arrow functions.
### Variables
Now, with ES6, there are three ways of defining your variables: ```var```, ```let```, and ```const```.
### var
``` var x = 5.6; ```
1. If you use var outside of a function, it belongs to the global scope.
2. If you use var inside of a function, it belongs to that function.
3. If you use var inside of a block, i.e. a for loop, the variable is still available outside of that block.
4. var has a function scope, not a block scope.
### let
``` let x = 5.6;```
1. let is the block scoped version of var, and is limited to the block (or expression) where it is defined.
2. If you use let inside of a block, i.e. a for loop, the variable is only available inside of that loop.
3. let has a block scope.

### const
```const x = 5.6;```
1. const is a variable that once it has been created, its value can never change.
2. const has a block scope.

