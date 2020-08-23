# Objects in JavaScript

## High Level Goals

By the end of this lesson, you will be familiar with the following:

- Defining an object
- Accessing values
- Assigning values
- Factory functions

## Objects

### What are Objects

An object is an unordered collection that consists of paired keys and values, there are no restrictions on data types when creating an object but usually, it is preferred to hold values that corresponds to what the value of the key should be.

Examples on defining an object:

```js
const object = {}; // => empty object

// in between the curly brackets `{}` add comma-separated paired key and value
// {name: "John Doe"} in the previous object the key (name) and the value (John Doe) are
// separated by a colon `:`
const name = { first: "John", last: "Doe" };

const numbers = { odd: [1, 3, 5], even: [2, 4, 6] };

const someObjectValues = {
  number: 100,
  string: "Hello World",
  array: [1, 2],
  boolean: true
  object: { a: 1 },
  square: function (number) {
    return number * number;
  },
};

// it is possible to use other variables inside the object
const firstName = "John";
const lastName = "Doe";

const fullName = { first: firstName, last: lastName };
```

### Accessing and Assigning values

In order to access a value in the object, we need to reference the object and its key name, there are two ways to do that dot notation and bracket notation

Here is an example

```js
const name = { first: "John", last: "Doe" };

// this is how dot notation looks like
name.first; // => "John"
name.last; // => "Doe"

// this is how bracket notation looks like
name["first"]; // => "John"
name["last"]; // => "Doe"

// bracket notation can be used with variables while dot notation can't be used with variables
const keyName = "first";

name[keyName]; // => "John"
name.keyName; // => undefined

// accessing nested objects
const nestedObjects = { name: { first: "John", last: "Doe" } };
nestedObjects.name.first; // => "John"
nestedObjects.name.last; // => "Doe"

// to assign new values or update existing ones, refer to the key and then use
// the assignment operator to update or add a new pair of key and value
let object = { firstKey: 10, secondKey: 20 };

object.firstKey = 100;
object; // => {firstKey: 100, secondKey: 20}
object["thirdKey"] = 30;
object.fourthKey = 40;
object; // => {firstKey: 100, secondKey: 20, thirdKey: 30, fourthKey: 40}
```

### Factory functions

In JavaScript, a factory function is a function that returns an object without using the keyword `new`

Example on factory functions:

```js
// people hold objects that represent a person
const people = [];

// imagine if we want to fill the people's array with twenty objects, it would be a bit tedious to
// create so many objects in this way to add to the array
const personOne = { name: "John", age: 23 };
const personTwo = { name: "Jane", age: 26 };

people.push(personOne, personTwo);
people; // => [{name:"John", age:23}, {name:"Jane", age:26}]

// so we could use a function to create the objects for us instead
const createPerson = function (name, age) {
  return { name: name, age: age };
};

personThree = createPerson("Mark", 19);
personFour = createPerson("Marry", 20);
people.push(personThree, personFour);
```

### Pulse Check

1. Define the following objects.

   ```js
   // 1- define an object `person` containing three attributes `name`, `age`, `gender`

   // 2- define an object `movie`containing three attributes `name`, `length`, `genre`

   // 3- define an object `favoriteFood` containing an array of your favorite foods

   // 4- define an object `store` containing two attributes, `name`, `address`, address is an object
   // with two attributes `buildingNumber`, `street`
   ```

2. Access the following values.

   ```js
   // 1- access the value of the key `Mars` in the following objects:

   // a- using dot notation
   const orderedSolarSystem = {
     Mercery: "first",
     Venus: "second",
     Earth: "third",
     Mars: "fourth",
   };
   // b- using bracket notation
   const unorderedSolarSystem = {
     Mars: "fourth",
     Earth: "third",
     Mercery: "first",
     Venus: "second",
   };

   // 2- access the value of key `koala` in the following object:
   const animalDiet = {
     mammals: {
       cat: "carnivore",
       dog: "carnivore",
       koala: "herbivore",
     },
     fish: {
       shark: "carnivore",
     },
   };
   ```

3. Assign the following values to the corresponding object.

   ```js
   // - add the math grade (80) to the student using dot notation
   // - change the english grade to an 90 using dot notation
   // - add an attribute average with the score of all three grades using dot notation
   const studentOne = {
     englishGrade: 80,
     scienceGrade: 90,
   };

   // - add the math grade (80) to the student using bracket notation
   // - change the english grade to an 90 using bracket notation
   // - add an attribute average with the score of all three grades using bracket notation
   const studentTwo = {
     englishGrade: 80,
     scienceGrade: 90,
   };

   // assign the following variables as a key-value pair to the object, make sure to
   //use the name of the variables
   const objectKey = "key";
   const ObjectValue = "value";

   const object = {};
   ```

### Practice

1. Figure out the syntax errors in the following, and fix them.

   ```js
   // 1
   const person = (name: john, age:20)

   // 2
   const car = {brand "Toyota", model: 2020}

   // 3
   const employee ={name: "Jane", position: developer}
   ```

2. Check the following objects and solve the requirements.

   ```js
   // - access the age property
   // - modify the person's age to be 23 years old
   // - add a property called `work` with the value of an object with two keys position and salary
   const person = {
     firstName: "John",
     lastName: "Doe",
     age: 24,
   };

   // - access the first name property of both employees
   // - add an employee object with your name and the position of full-stack developer
   const employees = [
     {
       id: 1,
       name: {
         first: "John",
         last: "Doe",
       },
       position: "Designer",
     },
     {
       id: 2,
       name: {
         first: "Jane",
         last: "Doe",
       },
       position: "Engineer",
     },
   ];

   // - access the model value of both cars
   // - change the prius model from 2019 to 2020
   // - add a new car of your choice
   // - add a property `isAutomatic` for all three cars
   const cars = {
     toyota: {
       name: "prius",
       model: 2019,
     },
     nissan: {
       name: "leaf",
       model: 2020,
     },
   };
   ```

3. Write a factory function `createCar` that accepts three string arguments `brand`, `name`, `color` and returns an object representing the car.

   ```js
   const createCar = function (brand, name, color) {
     // TODO: Your code here
   };

   createCar("Toyota", "Prius", "Black"); // => {brand: "Toyota", name: "Prius", color: "Black"}
   ```

4. Write a function `getFullName` that accepts an object representing a person and returns that person's full name in a string.

   ```js
   const getFullName = function (person) {
     // TODO: Your code here
   };

   getFullName({ first: "Elon", middle: "Reeve ", last: "Musk" }); // => "Elon Reeve Musk"
   getFullName({ first: "John", middle: "Mark ", last: "Doe" }); // => "John Mark Doe"
   ```

5. Write a function `olderThan` that accepts two objects `personOne`, `personTwo` and returns a string that represent who is older than the other.

   ```js
   const olderThan = function (personOne, personTwo) {
     // TODO: Your code here
   };

   olderThan({ name: "John", age: 23 }, { name: "Jane", age: 26 }); // => "Jane is older than John"
   olderThan({ name: "Mark", age: 30 }, { name: "Smith", age: 25 }); // => "Mark is older than Smith"
   olderThan({ name: "Marry", age: 20 }, { name: "Sarah", age: 20 }); // => "Marry is as old as Sarah"
   ```

### Extra Practice

1. Check the following object and solve the requirements.

   ```js
   // - access the value of Sarah's children and the value of Samuel's children
   // - add a child for Samuel named Sam that has two children Marry and Gwen
   // - delete the children property from the people who don't have children
   // HINT: read about the delete operator
   const family = {
     name: "John",
     children: [
       {
         name: "Bill",
         children: [
           {
             name: "Mark",
             children: [],
           },
           {
             name: "Sarah",
             children: [
               {
                 name: "Smith",
                 children: [],
               },
               {
                 name: "Stan",
                 children: [],
               },
             ],
           },
           {
             name: "Samuel",
             children: [],
           },
         ],
       },
       {
         name: "Jane",
         children: [],
       },
     ],
   };
   ```

2. Write a factory function `createIceCream` that accepts Three arguments `coneType`, `iceCreamFlavour`, `topping` and returns and object representing the ice-cream.

   ```js
   const createIceCream = function (coneType, iceCreamFlavour, topping) {
     // TODO: Your code here
   };

   createIceCream("wafer cone", "chocolate"); // => {coneType: "wafer cone" iceCreamFlavour: "chocolate", topping: none}
   createIceCream("waffle cone", "vanilla", "chocolate syrup"); // => {coneType: "waffle cone", iceCreamFlavour: "vanilla", topping: "chocolate syrup"}
   createIceCream("sugar cone", "strawberry", "cherry"); // => {coneType: "sugar cone", iceCreamFlavour: "strawberry", topping: "cherry"}
   ```

3. Explain the following.

   ```js
   const employeeOne = {
     id: 0,
     name: "John",
     position: "",
   };

   const employeeTow = {
     id: 1,
     name: "Jane",
     position: "Developer",
   };

   // try the following and explain the results
   // 1
   if (employeeOne.id) {
     console.log(employeeOne.name);
   }
   // 2
   if (employeeTwo.id) {
     console.log(employeeOne.name);
   }
   //3
   if (employeeOne.title) {
     console.log(employeeOne.name);
   }
   //4
   if (employeeTwo.title) {
     console.log(employeeOne.name);
   }
   //5
   if (employeeOne.salary) {
     console.log(employeeOne.name);
   }
   ```

4. Write a function `isValidUser` that accepts an object representing login information and returns `true` if the User is valid otherwise return `false`, read the comments for more information.

   ```js
   // things to validate:
   // 1- length of the email is greater than or equal 6
   // 2- length of the password is greater than or equal 8
   // 3- email contains `@` and `.com`
   // 4- the user must be in the users object
   // 5- both of the passwords match
   // 6- when you compare information make sure to reference the users object and access the value form there
   const users = {
     mrpotato: {
       email: "mr.potato@gmail.com",
       password: "LonelyPotato",
     },
     thewiseman: {
       email: "wiseMan9999@gmail.com",
       password: "12345678",
     },
   };

   const isValidUser = function (loginInfo) {
     // TODO: Your code here
   };

   isValidUser({
     username: "MrPotato",
     email: "mr.potato@gmail.com",
     password: "LonelyPotato",
   }); // => true

   isValidUser({
     username: "MrPotato",
     email: "mr.potato@gmail.com",
     password: "Lonely",
   }); // => false

   isValidUser({
     username: "MrPotato",
     email: "mr.potato.gmail.com",
     password: "LonelyPotato",
   }); // => false
   ```

5. Write a function `isPropertyOf` that accepts a string and an object and return `true` if the string is a property of the object and return `false` if it isn't.

   ```js
   const isPropertyOf = function (string, object) {
     // TODO: Your code here
   };

   isPropertyOf("hello", { hello: "world" }); // => true
   isPropertyOf("world", { hello: "world" }); // => false
   ```
