# Iteration in JavaScript

## High Level Goals

By the end of this lesson, you will be familiar with the following:

- Defining a while loop
- Defining a for loop
- Iterate over arrays, objects

## Iteration With While And For Loops

### What Are Loops

Loops execute a snippet of code repeatedly, they are used to make our code dynamic and more readable, loops consist of three parts, a starting point, a step, and a run condition.

There are multiple ways of creating loops, we will be learning the two most common types, for loops and while loops

Example on defining a while loop:

```js
// create a starting point
let i = 0;
// define the while loop with the right condition
while (i < 5) {
  // code to execute
  console.log(i);

  // increment the i
  i++;
}
// => 0
// => 1
// => 2
// => 3
// => 4
```

Examples on defining a for loop:

```js
// in the first section initialize the variables that will be used in the loop and separate it from the other sections by using ";"
// in the middle part define the run condition, if the condition is true then the loop's code will be executed
// in the last part add a step that gets the loop to reach the endpoint (when the run condition is false)
for (let i = 0; i < 5; i++) {
  console.log(i);
}
// => 0
// => 1
// => 2
// => 3
// => 4

// an example of defining a for loop with more than one variable
for (let i = 0, j = 10; i != j; i++, j--) {
  console.log(i, j);
}
// => 0 10
// => 1 9
// => 2 8
// => 3 7
// => 4 6
```

### Iteration With Arrays

Since arrays are indexed then it makes sense if we are trying to access all of it's content to create a loop with the starting point of zero since that is the starting index of the array
and the endpoint of the length of the array minus one.

Here is an example:

```js
// write a function that takes an array of numbers and returns a new array with the positive numbers only
const positiveOnly = function (numbers) {
  const result = [];
  // for (let i = 0; i < numbers.length; i++) {
  //   if (numbers[i] >= 0) {
  //     result.push(numbers[i]);
  //   }
  // }

  // let index = 0
  // while(index < numbers.length){
  //     if (numbers[index] >= 0){
  //         result.push(numbers[index]);
  //     }
  //     index ++
  // }
  return result;
};
```

### Iteration With Objects

Since objects aren't indexed like arrays then the previous ways won't work with objects, it is recommended to use the `for in loop` when dealing with objects.

Since ECMAScript 2015, objects do preserve creation order for string and Symbol keys. In JavaScript engines that comply with the ECMAScript 2015 spec, iterating over an object with only string keys will yield the keys in order of insertion.

An example on for in loop

```js
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
};

for (key in person) {
  console.log(key, person[key]);
}
// => firstName John
// => lastName Doe
// => age 50
```

### Common Mistakes While Using Loops

```js
// incorrect condition, will not enter the while block
let index = 0;
while (index < -10) {
  console.log(index);
  index++;
}

// wrong or no step, will result in an infintie loop
let index = 0;
while (index < 10) {
  console.log(index);
  index--;
}

// modifying the index by other code outside the while loop
let index = 0;
while (index < 10) {
  console.log(index);
  index++;
}

// since the first while loop ran, it modified the index value to be equal to 9
// and that would result in not executing the second while loop because the condition will be false
while (index < 9) {
  console.log(index);
  index++;
}
```

### Pulse Check

1. What are the three main parts of loops?.

2. Create a while loop with the starting value of 0 and end value of 5 and console log all numbers in between including the start and end.

3. Create a for loop with the starting value of 10 and end value of 20 and console log all numbers in between including the start and end.

4. Create a for in loop that works on the following object and console log both the key and value.

   ```js
   const object = {
     one: 1,
     two: 2,
     three: 3,
     four: 4,
   };
   ```

### Practice

1. Write a function `sum` that accepts an array of numbers and returns the sum of the numbers.

   ```js
   const sum = function (numbers) {
     // TODO: Your code here
   };
   sum([1, 2, 3, 4, 5, 6]); // => 21
   ```

2. Write a function `onlyOddNumbers` that accepts an array of numbers and returns a new array with only the odd numbers.

   ```js
   const filter = function (numbers) {
     // TODO: Your code here
   };
   filter([0, 1, 2, 3, 4, 5, 6]); // => [1, 3, 5]
   ```

3. Write a function `maximumNumber` that accepts an array of numbers and returns the max number in the array.

   ```js
   const maximumNumber = function (numbers) {
     // TODO: Your code here
   };
   maximumNumber([0, 5, 2, 10, 8, 6]); // => 10
   ```

4. Write a function `totalBill` that accepts an object representing separate bills and returns the sum of all bills.

   ```js
   // Make sure to loop over the bills object
   const bills = {
     waterBill: 25,
     electricityBill: 50,
     hospitalBill: 1000,
   };

   const totalBill = function (billsObject) {
     // TODO: Your code here
   };
   totalBill(bills); // => 1075
   ```

5. Write a function `validateMessage` that accepts an object representing a message and return the object if it is valid and after removing any extra keys, the message will consist of three keys `username`, `message`, `date` with all of their values as strings return the object only if all three keys are strings, if the number of keys is more than three then delete the extra keys, if the message doesn't have the right data type then return `invalid message`

   ```js
   const messageOne = {
     username: "John",
     message: "Hello",
     date: "01/01/2020",
     someKey: "someValue",
   };

   const messageTow = {
     username: 10,
     message: "Hello",
     date: "01/01/2020",
   };

   const messageTow = function (message) {
     // TODO: Your code here
   };
   messageTow(messageOne); // => {username: "John", message: "Hello", date:"01/01/2020"}
   messageTow(messageTow); // => invalid message
   ```

### Extra Practice

1. Write a function `onlyEven` that accepts an array of numbers and returns the same array with only the even numbers.

   ```js
   // make sure to use the same array
   const onlyEven = function (numbers) {
     // TODO: Your code here
   };
   onlyEven([0, 1, 2, 3, 4, 5, 6]) // =>[0, 2, 4, 6]
   onlyEven([1, 9, 2, 3, 4) // => [2, 4]
   ```

   HINT: check out how the method `splice` with arrays

2. Write a function `sort` that accepts an unordered array of numbers and returns the same array in a descending order.

   ```js
   // make sure to use the same array
   const sort = function (numbers) {
     // TODO: Your code here
   };

   sort([0, 1, 2, 3, 4, 5, 6]); // => [6, 5, 4, 3, 2, 1, 0]
   sort([3, 6, 2, 0, 4, 1, 5]); // => [6, 5, 4, 3, 2, 1, 0]
   ```

3. Write a function `compare` that accepts an object with numerical keys and returns an array containing the values with the corresponding index.

   ```js
   const convertToArray = function (object) {
     // TODO: Your code here
   };

   convertToArray({ 0: "one", 1: "two", 2: "three" }); // => ["one", "two", "three"]
   ```

4. Write a function `compare` that accepts an array and an object and returns true if all the array values are present as object values.

   ```js
   const compare = function (array, object) {
     // TODO: Your code here
   };

   compare(["one", "two", "three"], { 0: "one", 1: "two", 2: "three" }); // => true
   compare(["one", "two", "four"], { 0: "one", 1: "two", 2: "three" }); // => false
   compare(["one", "two"], { 0: "one", 1: "two", 2: "three" }); // => true
   compare(["one", "two", "three"], { 0: "one", 1: "two" }); // => false
   ```

5. Write a function `deleteKeys` that accepts an array and an object and returns the same object after removing all key-value pairs depending on the values in the array, the array will contain the key names that must be removed from the object.

   ```js
   const deleteKeys = function (array, object) {
     // TODO: Your code here
   };

   deleteKeys(["one", "two"], { one: "one", two: "two", three: "three" }); // => { one: "one", two: "two", three: "three" }
   deleteKeys(["four", "five", "one"], { 0: "one", 1: "two", 2: "three" }); // => { two: "two", three: "three" }
   ```

6. Write a function `sum` that returns the sum of all arguments passed to the function, make sure not to use parameters.

   ```js
   const sum = function () {
     // TODO: Your code here
   };

   sum(1, 2); // => 3
   sum(1, 2, 3, 4); // => 10
   sum(4, 5, 6, 7, 8); // => 30
   sum(1); // => 1
   sum(); // => 0
   ```

   HINT: read about `arguments`.
