# Arrays in JavaScript

## High Level Goals

By the end of this lesson, you will be familiar with the following:

- Defining an array
- Accessing array values
- Assigning values to arrays
- Array methods

## Arrays

### What are Arrays

An array is an ordered collection of related values, there are no restrictions on data types when creating an array but usually, it is preferred to hold values of the same data type.

Examples on defining an array:

```js
const array = []; // => empty array

// in between the square brackets `[]` add comma-separated values
// the values of an array could be of any data type
const fruits = ["Apple", "Banana", "Strawberry", "Mango"];
const oddNumbers = [1, 5, 7, 3, 11];
const someArrayValues = [
  100,
  "Hello",
  true,
  [1, 2, 3, 4],
  function () {
    console.log("Hello");
  },
];

// it is possible to use other variables inside the array
let nameOne = "John";
let nameTwo = "Doe";
const names = [nameOne, nameTwo];

names; // => ["John", "Doe"]

nameOne = "Jane";
nameTwo = "Smith";

names; // => ["John", "Doe"]
```

### Accessing and Assigning values

In order to access a value in the array, we need to reference its location in the array, since arrays are indexed we will need to reference the index of the element to access its value

Here is an example:

```js
// the array indexes start at 0 so the first item in the array will always have the index of 0
const numbers = [40, 30, 90, 45];

// to access a value  we need to reference the array and then add the index number in between square brackets
numbers[0]; // => 40
numbers[1]; // => 30
numbers[2]; // => 90
numbers[3]; // => 45
numbers[4]; // => undefined

// arrays come with a property called `length` that is used to get the length of the array,
// it could be used to access the last element of an array
numbers.length; // => 4
numbers[numbers.length - 1]; // => 45

// accessing nested arrays
const nestedArrays = [
  [1, 2, 3],
  [4, 5, 6],
];

nestedArrays[0]; // => [1,2,3]
nestedArrays[0][1]; // => 2
nestedArrays[1][0] === 4; // => true

// now since we can access a specific location in the array, we can use the assignment operator to update or add values
const nums = [5, 2, 3];

nums[0] = 1;
nums; // => [1, 2, 3]
nums[3] = 4;
nums; // => [1, 2, 3, 4]
```

### Array Methods

Arrays have some built-in methods that we can use to manipulate the array, some of them are `push`, `pop`, `shift` and `unshift`

An example of array methods:

```js
// the array's push method is used to add one or more elements  to the end of the array
const numbers = [1, 2];
numbers.push(3);
numbers; // => [1, 2, 3]
numbers.push(4, 5);
numbers; // => [1, 2, 3, 4, 5]

// the array's `pop` method is used to remove the last element of the array
numbers.pop();
numbers; // => [1, 2, 3, 4]

// the array's `shift` method is used to remove the first element of the array
numbers.shift();
numbers; // => [2, 3, 4]

// the array's `unshift` method is used to add one or more elements to the start of the array
numbers.unshift(1);
numbers; // => [1, 2, 3, 4]
numbers.unshift(-1, 0);
numbers; // => [-1, 0, 1, 2, 3, 4]
```

### Pulse Check

1. Define the following arrays.

   ```js
   // 1- define an array `colors` containing your favorite three colors

   // 2- define an array `negativeNumbers`containing negative numbers

   // 3- define an array `food` containing three of your favorite foods

   // 4- define an array `numbers` containing two arrays, the first containing three odd numbers and
   // the second containing four even numbers
   ```

2. Access the following values.

   ```js
   // 1- access the value `Mars` of the following arrays using the index
   const orderedPlanets = ["Mercery", "Venus", "Earth", "Mars", "Jupiter"];
   const unorderedPlanets = ["Mars", "Earth", "Mercery", "Jupiter", "Venus"];

   // 2- access the `Koala` value of the following arrays using the `length` property
   const animals = ["Cat", "Dog", "Dolphin", "Squirrel", "Koala"];

   //  3- access the  middle value of the following array using the `length` property or the index
   const cars = ["Ford", "BMW", "Ferrari", "Mercedes", "Subaru"];
   ```

3. Assign the following values to the corresponding array.

   ```js
   // 1- Assign the value `Mars` to end of the following arrays (don't replace `Jupiter` and `Mercery`)

   // a- use the `length` property
   const orderedPlanets = ["Mercery", "Venus", "Earth", "Jupiter"];
   // b- don't use the `length` property (use the index)
   const unorderedPlanets = ["Mars", "Earth", "Mercery"];

   // 2- Assign the `Koala` to the start of the following array (replace `Cat`)
   // use the index
   const animals = ["Cat", "Dog", "Dolphin", "Squirrel"];

   //  3- Assign the value `Toyota` to the middle of the following array using the `length` property(replace `Ferrari`)
   const cars = ["Ford", "BMW", "Ferrari", "Mercedes", "Subaru"];
   ```

4. Solve the following questions while using array methods.

   ```js
   // 1- add an the value 'Dinosaur' to the end of the array using the correct array method
   const reptiles = ["Snake", "Lizard", "Turtle"];

   // 2- add an the value 'Goldfish' to the start of the array using the correct array method
   const fish = ["Swordfish", "Clownfish", "Shark"];

   // 3- remove the first value of `reptiles`

   // 4- remove the last value of `fish`
   ```

### Practice

1. Check out the following examples and solve the question

   ```js
   // split: is used to convert a string into an array and the values will be separated depending on the
   // argument passed into the split method
   const word = "Hello";
   // if an empty string is passed as an argument then the string will be split on every letter
   word.split(""); // => ["H", "e", "l", "l", "o"]
   // if a string contains empty space then the string will be split on every empty space
   const words = "This is a string that contains words";
   words.split(" "); // => ["This", "is", "a", "string", "that", "contains", "words"]

   // join: is used to converting an array into a string and the values will be separated depending on the
   // argument passed into the join method
   const names = ["John", "Doe"];
   const fullName = names.join("-");
   fullName; // => "John-Doe"

   // reverse: is used to reverse the order of the array
   const numbers = [1, 2, 3, 4];
   numbers.reverse(); // => [4, 3, 2, 1]

   // write a function `reverseWords` that accepts a string argument and returns the same string if only
   // one word was passed in, and if more than one is passed it will return a string of the words in a reverse order

   const reverseWords = function(string){
       // TODO: Your code here
   }

   reverseWords("Hello"); // => "Hello"
   reverseWords("Hello World"); // => "World Hello"
   ```

   HINT: check the previous question for inspiration

2. Write a function `addToLast` that accepts two arguments an `array`, `value` and returns an array with the value added to the end of the array while using `unshift` instead of push

   ```js
   // do not use `push` or array assignments, only `unshift`
   const addToLast = function (array, value) {
     // TODO: Your code here
   };

   addToLast([1, 2, 3], 4); // => [1, 2, 3, 4]
   addToLast([10, 6], 1); // => [10, 6, 1]
   ```

3. Solve the following

   ```js
   // write a function `getLength` that accepts an array and returns the
   // length of the array without using the array's attribute `length`
   const getLength = function (array) {
     // do not use array.length
     // TODO: Your code here
   };

   getLength([1, 2, 3, 4]); // => 4

   // write a function `getFirstVal` that accepts an array and returns the
   // first value of the array without using the index to access the value
   const getFirstVal = function (array) {
     // do not use array[0]
     // TODO: Your code here
   };

   getFirstVal([1, 2, 3, 4]); // => 1
   ```

   HINT: check out the return value of `push`, `pop`, `shift` and `unshift`

4. Write a function `updateOrCreate` that accepts three arguments an `array`, `value`, `index` and returns an updated array, check the output for more information on the updated array

   ```js
   const updateOrCreate = function (array, value, index) {
     // TODO: Your code here
   };

   updateOrCreate([10, 20, 30], 50, 1); // => [10, 50, 30]
   updateOrCreate([10, 20, 30], 40, 3); // => [10, 20, 30, 40]
   updateOrCreate([10, 20, 30], 100, 10); // => [10, 20, 30, empty * 7, 100]
   ```

5. Read about `slice` and `indexOf` and answer the following

   ```js
   //  Write a function `sliceArray` that accepts three arguments an ordered numeric `array`, `startVal`, `endVal`
   // and returns an array starting at the `startVal` and ending at `endVal`

   const sliceArray = function (array, startVal, endVal) {
     // TODO: Your code here
   };
   sliceArray([10, 20, 30, 40, 50, 60], 10, 60); // => [10, 20, 30, 40, 50, 60]
   sliceArray([10, 20, 30, 40, 50, 60], 20, 40); // => [20, 30, 40]
   sliceArray([10, 20, 30, 40, 50, 60], 20, 20); // => []
   sliceArray([10, 20, 30, 40, 50, 60], 50, 20); // => []
   ```

### Extra Practice

1. Write a function `isPalindrome` that accepts a string argument and returns whether the string is a palindrome or not.

   ```js
   // a palindrome is when a string is read the same backwards
   const isPalindrome = function () {
     // TODO: Your code here
   };

   isPalindrome("dad"); // => true
   isPalindrome("was it a car  or a cat i saw"); // => true
   isPalindrome("a santa at nasa"); // => true
   isPalindrome("John doe"); // => false
   ```

   HINT: using `join` and `split` try to git rid of the white spaces in the string

2. Write a function `randomFruit` that accepts an array of fruits and returns a random element from that array.

   ```js
    const randomFruit = function (array) {
      // TODO: Your code here
    };

    const fruits = ["Apple", "Banana", "Strawberry", "Mango"];

    randomFruit(fruits; // => Apple
    randomFruit(fruits; // => Apple
    randomFruit(fruits; // => Strawberry
    randomFruit(fruits; // => Banana
   ```

   HINT: search for `Math.random` on [MDN](https://developer.mozilla.org/en-US/)

3. Write a function `convertToString` that accepts an array of strings and returns a string made out of the array values.

   ```js
   const convertToString = function (array) {
     // TODO: Your code here
   };

   convertToString(["Hello", "i", "am", "John", "Doe"]); // => Hello i am John Doe
   convertToString(["Hello", "John", "i", "am", "Jane"]); // => Hello John i am Jane
   ```

4. Write a function `search` that accepts an array of strings and a string then returns whether the string is inside of the array or not.

   ```js
   const search = function (array, string) {
     // TODO: Your code here
   };

   const fruits = ["Apple", "Banana", "Strawberry", "Mango"];

   search(fruits, "Apple"); // => true
   search(fruits, "banana"); // => true
   search(fruits, "John"); // => false
   ```
