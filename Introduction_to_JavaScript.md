# Inroduction To JavaScript

## High Level Goals

By the end of this lesson, you will be familiar with the following:

- The definition of JavaScript
- Knowing the basic JavaScript value types
- Using the console to create JavaScript expressions

## JavaScript

### What is JavaScript (JS)

JavaScript is mainly client-side scripting or programming language that is used to implement dynamic features for the web, it can be run on most of the browsers and especially the mainstream browsers such as, Google Chrome, Firefox. Internet Explorer and Safari, to write and run JavaScript code on Google Chrome you can open the console by right-clicking the page then choosing inspect and lastly by opening the `Console` tab, you can also use the following shortcuts if you are on windows `Ctrl + Shift + i` or `F12` and on macOS you can use `Option + Command + i` or `F12`.

### What Is Syntax

In computer science, the syntax of a computer language is the set of rules that defines the combinations of symbols that are considered to be correctly structured statements or expressions in that language.

Try the following using the Console:

```js
// Using mathematical symbols it is possible to form a JavaScript expression
1 + 1;
3 * 4;
10 / 2;
```

### Basic Value Types

Let's take a look on some of the value types in JavaScript.

```js
// 1- Strings: a JavaScript string stores a series of characters
// to create a string wrap the characters with double or single quotes  => "", ''
"This is an example of what a string looks like", "Another one";

// to create an expression to combine strings together use the `+` operator, known as string concatenation
"Hello " + "World"; // => "Hello World"

// 2- Numbers
120, 300, -56, 0;

// to perform mathematical operations in JS combine numbers and operators (+, -, *, /, %) in an expression,
// also in JS these operations will follow the Mathematical order of operations (PEMDAS)
100 + ((10 - 5) * 2) / 5; // => 102
10 % 2; // => 0

// 3- Booleans
true, false;

// to create an expression that returns a boolean value use boolean operators or comparison operators
"Hello" === "World"; // => false
true && false; // => false
true || false; // => true
!true; // => false
5 > 4; // => true
```

### Mixing Types

Since JavaScript isn't a strictly-typed langauge it is possible to mix different values of different types together.

Try the following:

```js
// an example of concatinating a string with a number
"I am " + 10 + " years old"; // => I am 10 years old

// in other strictly-typed languages it is not possible to add integers and float numbers together
10 + 5.5; // => 15.5

// true has the value of 1 when added to other numbers, and false the value of 0
true + 3 + true; // => 5
```

Mixing types makes the langauge a little bit begginer friendly since not many errors will be thrown when trying to mix types which is a mistake done by begginers specially when it come to numbers.

### Writing A Program

Something that you need to understand about coding is that computers will follow all of the instructions provided in detail, unlike humans computers aren't capable of performing intuitive leaps while reading the instructions.

An example of an intuitive leap would be if you would ask another human to bring you a cup of tea, they will be able to intuitively understand a vague request so they will choose the right kind of tea (usually black if not specified or they can ask if they aren't sure) also they will bring sugar and choice the right kind of cup for it without you having to specify it, while computers on the other hand must have very detailed instructions in the right order to be able to fulfill the request.

Luckily, you will have ways to be able to communicate with the machine by using a common language such as JavaScript, in summary, to create a program you will have to provide a series of detailed instructions with a language your machine understands.

The code is read from top to bottom and from left to right, if you would like to add a comment in the program to explain some code you could use `//`, comments will be ignored while running the program.

An example of Understandable language:

```js
// In JavaScript you will have some keywords or symbols to make the communication easier

// an example of reserved keywords  => function, if , else , console
// an example of reserved symbols   => {}, [], <, >, "

// An example of combining symbols and some keywords to enable us to log the word `Hello` in the console
console.log("Hello");
```

### Practice

Open the console and solve the following questions

1. Predict the value of the following expressions then try them out in the console

    ```js
    9 + 1 * 5;  // ?
    9 % 2;  // ?
    (9 / 3) * (10 - 7);  // ?
    21 / 3 + (3 × 9) × 9 + 5;  // ?
    36 ÷ 9 + 48 - 10 ÷ 2;  // ?
    ```

2. Write an expression that represents the average grade of an exam, knowing that in a class of ten students, five of them got 24/30, 2 of them got 16/30 and the remaning ones got 29/30

3. Write an expression that represents the number of seconds in 30 days.

4. Using string concatenation write an expression that represents Your First name, Last name, Gender, and Nationality

5. Before trying the following expressions try to predict the outcome

    ```js
    10 + "10"; // ?
    "10" + "10"; // ?
    10 + 10 + "5"; // ?
    "Hello" + 1; // ?
    false - true; // ?
    ```
