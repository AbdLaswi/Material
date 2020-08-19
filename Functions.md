# Functions In JavaScript

## High Level Goals

By the end of this lesson, you will be familiar with the following:

- The definition of functions
- Creating a function and invoking it
- Understanding parameters and arguments
- Using the functions as values

## Functions

### What Are Functions

A function is a snippet of code (instructions to perform a specific action), that can be called(executed) by other code or by itself, In order to invoke(call) the function you will have to use the name of the function followed by parentheses `()`, There are functions that are called `anonymous function` that do not have a specified name.

There are two ways of creating a function, `function declaration`, and `function expression`, for this lesson we will focus on creating functions using function expressions.

Something to keep in mind, while naming functions, parameters, variables in JS, that it is considered good practice to write the names using camel case, meaning to always start the first word with a small letter and for the rest of the following words use a capital letters for the first letter of each word, `calculateAgeInMinutes`, `cube`.

### Define A Function

The basic syntax for creating functions:

```js
// an example for defining a function named "ourFunction" by using a function expression.
const ourFunction = function () {
  // Executable code
};

// an example for defining a function named "ourFunction" by using function declaration
function ourFunction() {
  // Executable code
}
```

You might have noticed the similarities with both ways but to explain them in more details.

`function`: is a reserved keyword that indicates the intent to define a function.

`parentheses ()`: contain the parameters that we will use in our function.

`curly brackets {}`: contains the executable code if any is present in the function.

when it comes to invoking the function both of the ways can be invoked in the same way which is by adding parentheses in front of the function name `ourFunction()`.

### Parameters And Arguments

In order to make our functions receive inputs we have to use parameters, we add parameters in between the parentheses
and use them in the code and whenever the value of the parameter is passed in to the function the parameters will be replaced with the real value.

let's create a function that prints out an introduction about yourself

```js
// the function has two parameters the "name", and "age" that need to be provided as arguments when invoking the function
const introduction = function (name, age) {
  // console.log() is an invocation of a method that will print on the console the arguments passed to it.
  console.log("Hello my name is " + name + " and i am " + age + " years old");
};

//when invoking the function we pass in the arguments in between the parentheses, make sure to use propper syntax
//use the right value types, and to pass the arguments in the correct order.
introduction("John", 20); // => Hello my name is John and i am 20 years old
introduction("Mark", 28); // => Hello my name is Mark and i am 28 years old
```

Let's create a function that squares the value passed.

```js
const square = function (number) {
  console.log(number * number);
};
```

### Functions As Values

In the previous examples we were printing out the result and that isn't helpful especially if we need to use the output of the function as a value somewhere else in the code, in order for the function to have a value we need to use the keyword 'return' in the body of the function.

let's explore how can functions have values below

```js
const add = function (numberOne, numberTwo) {
  return numberOne + numberTwo;
};

const subtract = function (numberOne, numberTwo) {
  return numberOne - numberTwo;
};

// if we invoke the function it should return a value
add(10, 20); // => 30
subtract(10, 5); // => 5

// we can use the return value of a function in other parts of the code, like the following example
10 + add(5, 5) + subtract(10, 8); // => 22
add(add(5, 5), 5); // => 15

// what is the value of the function if we do not use the return keyword?
const multiply = function (numberOne, numberTwo) {
  numberOne * numberTwo;
};

multiply(5, 5); // => undefined
```

### Practice

1. Figure out the syntax errors in the following functions, and fix them

   ```js
   const myFunction = function parameter) {}
   const my Second Function = function (parameter) {}
   const function = function (parameter) {}
   const functionName = function (paramOne paramTwo) {}
   ```

2. Write a function `fullName` that accepts string arguments, firstName and lastName then returns a string containing your full name combined

   ```js
   const fullName = function (firstName, lastName) {
     // TODO: Your code here
   };

   fullName("John", "Doe"); // => "John Doe"
   fullName("Mark", "Smith"); // => "Mark Smith"
   ```

3. Write a function `average` that accepts two number arguments and returns the average of these numbers

   ```js
   const average = function (a, b) {
     // TODO: Your code here
   };

   average(20, 25); // => 22.5
   average(15, 7); // => 11
   ```

4. Using the defined functions below and your average function to guess the output of the following expressions

   ```js
   const square = function (number) {
     return number * number;
   };

   const cube = function (number) {
     return number * number * number;
   };

   // guess the following
   cube(25) + 20; // => ?
   square(5) + cube(2); // => ?
   square(10 / 5) + cube(2 + 1); // => ?
   average(square(average(6, 2)), cube(4)); // => ?
   ```

5. Write a function `toThePowerOf` that accepts two number arguments, `base`, `exponent` and returns the base to the exponent power.

```js
const toThePowerOf = function (base, exponent) {
  // TODO: Your code here
};

toThePowerOf(2, 3); // => 8
toThePowerOf(4, 2); // => 16
```

HINT: Look up Math.pow() on [MDN](https://developer.mozilla.org/en-US/)

### Extra Practice

1. Write a function `floor` that accepts one number argument, `number` and returns the number as an integer.

   ```js
   const floor = function (number) {
     // TODO: Your code here
   };

   floor(5); // => 5
   floor(2.4); // => 2
   floor(0.2); // => 0
   ```

   HINT: Look up Math on [MDN](https://developer.mozilla.org/en-US/) and find the correct built in method to use.

2. Write a function `calculateProfit` that accepts three arguments `unitsSold`, `unitCost`, `unitPrice` and returns the net profit.

   ```js
   const calculateProfit = function (unitsSold, unitCost, unitPrice) {
     // TODO: Your code here
   };

   calculateProfit(10, 5, 15); // => 100
   calculateProfit(4, 2, 5); // => 12
   ```

3. Write a function `calculateTotalBillAmount` that accepts three arguments `total`, `taxPercentage`, `tip` and returns the total after adding the tax and the tip.

   ```js
   const calculateTotalBillAmount = function (total, taxPercentage, tip) {
     // TODO: Your code here
   };

   calculateTotalBillAmount(40, 0.16, 2); // => 48.4
   calculateTotalBillAmount(10, 0.16, 0); // => 11.6
   ```

4. Write a function `ageInDays` that accepts a number argument `ageInYears` and returns the age in days (ignore leap years).

   ```js
   const ageInDays = function (ageInYears) {
     // TODO: Your code here
   };

   ageInDays(10); // => 3650
   ageInDays(19); // => 6935
   ```

5. Write two functions `calculateConeVolume` and `calculateConeSurfaceArea` that accepts two number arguments height and radius and returns the volume and surface area for a `Right Circular Cone`

   ```js
   const calculateConeVolume = function (height, radius) {
     // TODO: Your code here
   };
   const calculateConeSurfaceArea = function (height, radius) {
     // TODO: Your code here
   };

   // your solution's return value might differ depending on the equation you used or the rounding,
   // in the following invocations the output is just an estimate not the exact value.
   calculateConeVolume(10, 6); // => ≈ 376
   calculateConeSurfaceArea(10, 6); // => ≈ 332
   ```
