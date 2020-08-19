# Variables In JavaScript

## High Level Goals

By the end of this lesson, you will be familiar with the following:

- Defining a variable
- Naming a variable
- Creating expressions using variables
- Scopes

## Variables

### What Are Variables

Variables are containers used for storing values, they are similar to variables in mathematics.

There are three main ways to declare a variable in JavaScript using three different keywords, `var`, `let`, and `const`, in the previous lesson about functions we have used the keyword `const` to define a function using `function expressions`.

### Defining A Variable And Assignment

The basic syntax for defining a variable:

```js
// the difference between const and let is that when using const it won't allow a new value to be reassigned to the variable,
// while when using let it allows the reassignment of values for the same variable
const ourVariable = "variable value";
let anotherVariable = 10;

// in order to reassign a value, you can just use the following syntax
ourVariable = 10; // => Uncaught TypeError: Assignment to constant variable.
anotherVariable = 20;

// to access the value of a variable just use it's name
anotherVariable; // => 20

// you can notice that the value of the variable stays the same even if the reference has changed (there are exceptions for this
// but it will be for a later lesson)
let a = 10;
let b = a;
a = 20;
a; // => 20
b; // => 10

// if you do not assign a value to the variable it will be given a value of undefined
let anotherVariable;
anotherVariable; // => undefined

const ourVariable; //Uncaught SyntaxError: Missing initializer in const declaration

// using the keyword var was the old way of defining variables, you can still see it being used but it is better to work with
// let and const instead.
var variableName = true;
```

### Naming Variables

When naming variables keep in mind the following:

- The name must begin with a letter or `$` or `_`.
- You can't name a variable with a reserved keyword.
- The name can contain a combination of letters, `$`, `_`, and digits.
- The name is case sensitive which means you can create a variable with the same name but different capitalization.
- This isn't a rule but it is a good practice to use camelCase while naming variables.
- Try to use descriptive names to make it easier to understand what the variable is supposed to hold by just reading the name.

```js
// valid variable names
let variable;
let $variable;
let _variable;
let variable10$$_1;

// invalid variable names (starting with digits or symbols other than $ and _)
let 10variable;
let #variable;

// invalid variable names (includes reserved keywords)
let var;
let let;
let function;
let const

```

### Scopes

Depending on where you have defined the variable you will be able to access it in a specific region only, and these regions are called scopes,
an example of such regions are functions, functions have their own local scope were variables exist in it and not outside of, so you can't refer to a variable declared in a function outside of it.

Variables can be accessed in all of the different scopes if the variable is declared in the global scope

let's explore scopes

```js
// global Scope
// an example of a global variable used in the local scope of a function

let name = "John";

const greet = function () {
  // start of local Scope
  return "Hello " + name;
  // end of local Scope
};

greet(); // => "Hello John"
name; // => "John"

/* ************************************************* */

// an example to show how the code is encapsulated within the function's scope and can't be accessed outside

const greeting = function (fName) {
  //Start of local Scope
  let firstName = fName;
  return "Hello " + firstName;
  //End of local Scope
};

greeting("Mark"); // => "Hello Mark"
firstName; // =>  Uncaught ReferenceError: firstName is not defined

/* ************************************************* */

// an example to show that it is possible to reassign values of a global variable in a local scope
let name = "Mark";

const updateName = function (newName) {
  name = newName;
  return name;
};

updateName("Jane"); // => "Jane"
name; // => "Jane"
```

### Pulse Check

1. Write the difference between const and let.

2. Define the following variables.

   ```js
   // 1- define a variable `color` containing your favorite  color

   // 2- define a variable `positiveNumber`containing any positive number

   // 3- define a variable `isLoggedIn` containing a boolean value

   // 4- define a variable `PhoneNumber` containing your phone number
   ```

3. Reassign the value of the following variables.

   ```js
   // 1- reassign the value to `Toyota`
   let myCar = "Nissan";

   // 2- reassign the value to a negative number
   let negativeNumber = 102;

   // 3- reassign the value to your name
   let name;

   // 4- reassign  the value of `a` to make the following expression equal to nine
   let a;
   let b = 3;
   let c = 10;

   c - b * c + a;
   ```

4. Create the following expressions.

   ```js
   // 1- create an expression to calculate the average grade for a class by using the following variables
   const totalClassGrades = 877;
   const numberOfStudents = 10;

   // 2- create an expression that represents a full name by using the following variables
   const firstName = "John";
   const lastName = "Doe";

   // 3- create an expression to calculate your age in seconds using the following variables
   const daysInYear = 365;
   const HoursPerDay = 24;
   ```

````

### Practice

1. Figure out the syntax errors in the following variable declarations, and fix them.

   ```js
   let @name = 'John';
   let 'age' = '10';
   let const = "Constant";
   let variable 1 = true;
   let true = true
````

2. Explain how the following variable declarations work.

   ```js
   let a;
   let b;
   let c;
   a = b = c = 20; // => a? b? c? expression value?
   a = b = c = 20 + 10; // => a? b? c? expression value?
   (a = b = c = 20) + 10; // => a? b? c? expression value?

   const var3 = 10;
   const ourFunction = function () {
     let var1 = 10;
     var2 = 10;
   };

   ourFunction();
   var3; // => var3?
   var2; // => var2?
   var1; // => var1?
   ```

3. Predict the value of the following variables and explain why

   ```js
   const d = 10;
   d = 20;
   d; // => d?

   let e = 5;
   let f = e;
   e = 10;
   f; // => f?

   let h = 1;
   let i = 10;
   h = i + 4;
   h + 20;
   i = h + 10;
   h; // => h?
   i; // => i?
   ```

4. Write a function `addToList` that accepts a string argument `toDo` and returns the current list as a string, every time we invoke the function it should return the old toDo item + the new one

   ```js
   const addToList = function (toDo) {
     // TODO: Your code here
   };

   addToList("Eat"); // => 'Eat'
   addToList("Play"); // => 'Eat Play'
   addToList("Sleep"); // => 'Eat Play Sleep'
   addToList("repeat"); // => 'Eat Play Sleep repeat'
   ```

5. Write two functions `deposit` and `withdraw` that accepts a number argument `amount` and returns the current account balance

   ```js
   const deposit = function (amount) {
     // TODO: Your code here
   };

   const withdraw = function (amount) {
     // TODO: Your code here
   };

   deposit(100); // => 100
   deposit(50); // => 150
   withdraw(70); // => 80
   deposit(50); // => 130
   withdraw(100); // => 30
   ```

### Extra Practice

1. Write a function `minMax` that accepts a number argument `number` and returns a string representing the maximum number and the minimum number, read the comments for more information.

   ```js
   // every time the function it is called it must check if the passed argument is the maximum number or minimum or
   // both and preserve the result for later invocations
   const minMax = function (number) {
     // TODO: Your code here
   };

   minMax(5); // => the maximum number is: 5 and the minimum number is 5
   minMax(2); // => the maximum number is: 5 and the minimum number is 2
   minMax(3); // => the maximum number is: 5 and the minimum number is 2
   minMax(7); // => the maximum number is: 7 and the minimum number is 2
   minMax(0); // => the maximum number is: 7 and the minimum number is 0
   ```

2. Predict the correct value of the variables.

   ```js
   const a = 10;
   let b = 1
   const functionOne = function () {
     b = 20;
     let c = 5
     const functionTwo = function () {
       let d = 5
       c = 8
       b = a + b + c + d
     };
     functionTwo()
   };
   const functionThree = function () {
     a = 20
   }

   functionOne();
   functionThree();

   a; // ?
   b; // ?
   c; // ?
   d: // ?
   ```

3. Modify the `rockPaperScissors` function from the previous lesson to save the score of how many times the user has won and how many the user has lost and return the score with every invocation.

   ```js
   // a function that randomly outputs `rock` or `paper` or `scissors`
   const random = function () {
     // gets a random number from 1-3
     const result = Math.ceil(Math.random() * 3);

     if (result === 1) {
       return "rock";
     } else if (result === 2) {
       return "paper";
     } else {
       return "scissors";
     }
   };

   // make sure to use the function above (random) to get a random output to compare with the user input

   const rockPaperScissors = function (move) {
     // TODO: Your code here
   };

   rockPaperScissors("rock"); // => "Won: 1, Lost:0"
   ```

4. Modify the `rockPaperScissors` function to have a score limit such as winning five times then reset the score back to zero.

   ```js
   // lets assume the score limit is set to three
   rockPaperScissors("rock"); // => "Won: 2, Lost:2"
   rockPaperScissors("rock"); // => "Won: 2, Lost:3"
   rockPaperScissors("rock"); // => "Won: 1, Lost:0"
   ```

5. Modify the `rockPaperScissors` function to keep track of the last winner and modify the `random` function to have a 25% chance of picking the same move if the user have lost the previous round other wise it picks a random move.

```js
rockPaperScissors("rock"); // => "Won: 0, Lost:1"
// lets assume that the same random move was picked because of the 25% chance
rockPaperScissors("rock"); // => "Won: 0, Lost:2"
rockPaperScissors("rock"); // => "Won: 1, Lost:0"
```
