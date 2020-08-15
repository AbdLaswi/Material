# Conditionals in JavaScript

## High Level Goals

By the end of this lesson, you will be familiar with the following:

- Booleans
- Comparisons operators
- Logical operators
- Conditional statements
- Truthy and falsy values

## Conditionals

### Booleans

Boolean is a data type in JavaScript that represent either `true` or `false`.

### Comparisons Operators

Comparison operators compare two values and return a boolean value that represents whether the expression is true or false.

Examples on comparison operators:

```js
// greater than, less than , greater or equal, less than or equal
10 > 5; // => true
10 < 5; // => false
10 >= 10; // => true
10 <= 5; // => false

// the `NOT` Logical operator `!` is used to reverse the logic state of the value, it is not a comparison operator but
// can be used with some comparison operators
!true; // => false
!false; // => true

// strictly equal operator `===` is used to compare if both values are equal and their types are the same,
// you can combine it with the `NOT` operator `!==` to check if the values aren't equal to each other
"Hello" === "World"; // => false
"Hello" !== "World"; // => true
5 === 5; // => true
5 === "5"; // => false

// loosely equal operator `==` is used to compare if both values are the same regardless of the type,
// it is not recommended to use this form of equality comparison because it may lead into unexpected results
5 == 5; // => true
5 == "5"; // => true
5 != "5"; // => false
```

### Logical Operators

Logical operators are used to evaluate an expression, even though logical operators are used to work with boolean values,
it is still possible to use them with other data types, for this lesson we will be using them to evaluate expressions that result in a boolean value.

Examples on logical operators:

```js
// the AND logical operator `&&` is used to evaluate if the whole statement is true or false, if both expressions/booleans are true
// then it will return true but if either of them is false it will return false
true && true; // => true
true && false; // => false
false && true; // => false
10 > 5 && "Hello" === "Hello"; // => true

// the OR logical operator `||` is used to evaluate if the whole statement is true or false, if either or both of
// the expressions/booleans are true then it will return true and if both are false it will return false
true || true; // => true
true || false; // => true
false || false; // => false
1 > 5 || "Hello" === "Hello"; // => true

// the NOT Logical operator `!` is used to reverse the logic state of the value, as mentioned before
!true; // => false
!false; // => true
```

### Conditional Statements

Conditional Statements are used to execute blocks of code if certain conditions are met, it is possible to chain multiple statements all together

Examples on conditional statements.

```js
// using the keyword `if` we can create a conditional statement that executes a block of code if the condition is true
if (true) {
  // run this block of code
}

/* ************************************************* */

if (1 < 10) {
  // run this block of code
}

/* ************************************************* */

// using the keyword `else` we specify a block of code to be executed if all previous conditions are false
if (false) {
  // since the condition is false, this block of code will be ignored
} else {
  // run this block of code
}

/* ************************************************* */

if (5 === 2) {
  // since the condition is false, this block of code will be ignored
} else {
  // run this block of code
}

/* ************************************************* */

// using the keyword `else if` it enable us to chain multiple conditions instead of just having an if/else statement
if (false) {
  // since the condition is false, this block of code will be ignored
} else if (true) {
  // run this block of code, because it was the first condition to succeed
} else if (true) {
  // even though this is also true it will not run since after executing the previous block of code it will stop checking
  // the other statements which result in this one being ignored
} else {
  // since one of the previous conditions is true, this block of code will be ignored
}

/* ************************************************* */

const name = "John";
if (name === "Mark") {
  // since the condition is false, this block of code will be ignored
} else if (name === "John") {
  // run this block of code
} else {
  // since one of the previous conditions is true, this block of code will be ignored
}

/* ************************************************* */

// truthy and falsy values
// in javaScript all values are considered truthy values, meaning that the value is considered true in a boolean context except
// falsy values which are considered false, some of the falsy values are `0`, `undefined`, `null`, `""` and `false`

if (1) {
  // run this block of code
}

if ("string") {
  // run this block of code
}

if (0) {
  // ignore this block of code
}

if (undefined) {
  // ignore this block of code
}
```

Example on what we have learnt so far:

```js
// Write a function `getGrade` that accepts a number argument and returns a string representing the grade
// 0  - 49  =>  F
// 50 - 59  =>  D
// 60 - 69  =>  C
// 70 - 79  =>  B
// 80 - 100  =>  A

const getGrade = function (grade) {
  if (grade >= 80) {
    return "A";
  } else if (grade >= 70) {
    return "B";
  } else if (grade >= 60) {
    return "C";
  } else if (grade >= 50) {
    return "D";
  } else {
    return "F";
  }
};

getGrade(90); // => A
getGrade(51); // => D
```

### Practice

1. Figure out the syntax errors in following, and fix them.

   ```js
   // 1
   if (10 =< 10){
   }

   // 2
   if 5 > 3 {
     return "Five bigger than three"
   }

   // 3
   if (false){
   }
   else(true){
   }

   // 4
   if (2 < 3 && 7 > 10)
   }

   // 5
   if ("hello" = "hello"){
   }
   ```

2. Predict the value of the expression and explain why

   ```js
   true && true && false;

   true || (true && false);

   5 === 2 || 1 < 10;

   (!false && true) || (!true && true);

   1 < 2 < 3;

   1 < 3 > 2;
   ```

3. Check out the following examples and solve the question.

   ```js
   // you could use the `toLowerCase` or `toUpperCase `string methods to check if a string matches without it being case sensitive
   "HeLlO wOrlD".toLowerCase() === "hello world"; // => true
   "HeLlO wOrlD".toUpperCase() === "hello world".toUpperCase(); // => true

   // one handy string property `length` is used to return the length of a string, could be useful
   //  if you are expecting the input to be in a certain length for example
   "myPassword".length <= 15; // => true
   "Hello World".length === 11; // => true, notice how even the empty space " " was counted as a character

   // Write a function `login` that accepts two string arguments `username` and `password` and
   // returns a string "login successful" if both are valid or return "Invalid login information" with the appropriate reason,
   // the function will check the following:
   // 1- if the length of the username is greater than 4
   // 2- if the username is of the specified usernames below
   // 3- if the password length is greater or equal to 8
   // 4- if the password is equal to the corresponding password
   // 5- the usernames don't need to be case sensitive but passwords do

   // (username => "MrPotato", password =>"LonelyPotato"),  (username => "theWiseMan", password => "12345678")
   const login = function (username, password) {
     // TODO: Your code here
   };

   login("MrPotato", "LonelyPotato"); // => login successful
   login("mrpotato", "LonelyPotato"); // => login successful

   login("MrPotato", "lonelypotato"); // => Invalid login information, wrong password or username
   login("MrPotato", "12345678"); // => Invalid login information, wrong password or username

   login("MrPotato", "123456"); // => Invalid login information, the password length must be greater or equal to 8
   login("mike", "12345678"); // => Invalid login information, the username length must be greater than 4
   ```

4. Write a function `isLeapYear` that accepts a number argument `year` and returns true if the year is a leap year, leap years are divisible by 4 but non leap years are not divisible by 100 for the exception of 400 (leap years are also divisible by 400)

   ```js
   const isLeapYear = function (year) {
     // TODO: Your code here
   };
   ```

5. Write a function `deposit` that accepts an argument `amount` and returns the deposited amount, the function should only accept positive number arguments otherwise return "Please enter a valid number"

   ```js
   const deposit = function (amount) {
     // TODO: Your code here
   };

   deposit(100); // => 100
   deposit("100"); // => Please enter a valid number
   ```

HINT: read about how to use `typeof` on MDN

### Extra Practice

1. Check out the following examples and solve the question..

   ```js
   // since strings store a series of characters in an ordered way
   // we could use the index of the character to access the character in the string
   // each character in the string has it is own unique identifying number (index),
   // the index value starts at zero and for every letter that is added after the first one the index will be incremented by one

   "hello"[0]; // => h
   "hello"[1]; // => e
   "hello"[2]; // => l
   "hello"[3]; // => l
   "hello"[4]; // => o

   // write a function `startsWith` that accept two string arguments `string`, `character` and returns true if the string
   // starts with that character

   const startsWith = function (string, character) {
     // TODO: Your code here
   };
   startsWith("Hello", "h"); // => true
   startsWith("World", "h"); // => false
   ```

2. Write a function `endsWith` that accept two string arguments `string`, `character` and returns true if the string ends with that character.

   ```js
   const endsWith = function (string, character) {
     // TODO: Your code here
   };

   endsWith("Hello", "o"); // => true
   endsWith("World", "h"); // => false
   ```

3. Write a function `rockPaperScissors` that accepts a string argument with only the following values, `rock`, `paper`, `scissors` and returns `invalid move` if anything else is passed and return `you win`, `you lose`, and `it is a draw` depending on the user input and the random selected move, read the comments for more explanation.

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
   random(); // => rock
   random(); // => paper  

   // rock beats scissors
   // paper beats rock
   // scissors beats paper
   const rockPaperScissors = function (move) {
     // use randomMove to get the value of the random move
     const randomMove = random()
     // randomMove; => rock (use it by referencing the name)
     // TODO: Your code here
   };

   rockPaperScissors("rock"); // => you win
   rockPaperScissors("rock"); // => you win
   rockPaperScissors("rock"); // => you lose
   rockPaperScissors("rock"); // => you win
   rockPaperScissors("rock"); // => it is a draw

   ```

4. Write a function `guessTheSquareRoot` that accepts two number arguments `number`, `squareRoot` and returns a string `correct` if the guess is correct and returns `incorrect` if the guess is incorrect.

   ```js
   const guessTheSquareRoot = function (number, squareRoot) {
     // TODO: Your code here
   };

   guessTheSquareRoot(4, 2); // => correct
   guessTheSquareRoot(4, 3); // => incorrect
   ```

   HINT: search for the correct method to use on [MDN](https://developer.mozilla.org/en-US/)

5. Write a function `search` that accepts two string arguments `string`, `letter` and returns `true` if the letter is inside the string and returns `false` if it doesn't.

   ```js
   const search = function (string, letter) {
     // TODO: Your code here
   };

   search("Hello", "E"); // => true
   search("Hello", "Z"); // => false
   ```

   HINT: search for the correct method to use on [MDN](https://developer.mozilla.org/en-US/)
