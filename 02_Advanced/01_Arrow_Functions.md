### Topics to discuss:

- Functional Programming
- Arrow functions
- Array Iteration Methods

[Slides](https://docs.google.com/presentation/d/1j9_ilYMYu5nd_VCJiy7t8v_ok3bC6qTvwqu-B3l4C3M/edit?usp=sharing)

# Functional Programming

## [Functional Programming Slide](https://docs.google.com/presentation/d/1j9_ilYMYu5nd_VCJiy7t8v_ok3bC6qTvwqu-B3l4C3M/edit#slide=id.g4533db2398_0_0)

Functional Programming is where you can pass a function as a parameter, store a function in a variable/constant, and define functions without names. All those may sound strange to you, but you'll see their value in due time.

So here's a basic function:

```javascript
// usual
function hello() {
  console.log("Hello");
}

hello();
```

and then let's redefine it as an anonymous function (a function without a name) stored in a variable:

```javascript
// functional
const helloAgain = function () {
  console.log("Hello Again");
};

helloAgain();
```

You'd call the function defined in this way the same way.

Let's say you have the following function:

```javascript
const performMath = function (operation, firstNum, secondNum) {
  return operation(firstNum, secondNum);
};
```

It's a function that takes an operation function and applies it on the two given numbers that follow. So this function doesn't know whether the operation is addition, subtraction, or what. Here's how you can use a function like this:

```javascript
const addition = function (firstNum, secondNum) {
  return firstNum + secondNum;
};

const subtraction = function (firstNum, secondNum) {
  return firstNum - secondNum;
};

const multiplication = function (firstNum, secondNum) {
  return firstNum * secondNum;
};

console.log(performMath(addition, 5, 3));
```

Here we're defining functions for addition, subtraction, and multiplication. We're _passing as parameter_ the addition function to `performMath()`. The output of this will be:

```
8
```

Given that `performMath()` receives a function as a parameter, that function can be defined in-line without giving it a name. Like this:

```javascript
console.log(
  performMath(
    function (a, b) {
      return a / b;
    },
    15,
    3
  )
);
```

You're defining a function here and passing it as a parameter. It doesn't need to be given a name here.

Here's a more complex example of defining an anonymous function:

```javascript
console.log(
  performMath(
    function (a, b) {
      const remainder = a % b;
      return `The remainder of ${a} / ${b} is ${remainder}`;
    },
    15,
    3
  )
);
```

# Arrow Function Notation

## Basic Arrow Function/No Parameters

There's another way of defining a function in JavaScript, using _arrow notation_. Here's a simple example:

```javascript
const helloArrows = () => {
  console.log("Hello, Arrows!");
};

helloArrows();
```

It's the same as before, but without using the `function` keyword. Any parameters a function might have can be in the `()` before the arrow `=>`. Let's re-write all the mathematical functions using arrow notation:

```javascript
const performMath = (operation, firstNum, secondNum) => {
  return operation(firstNum, secondNum);
};

const addition = (firstNum, secondNum) => {
  return firstNum + secondNum;
};

const subtraction = (firstNum, secondNum) => {
  return firstNum - secondNum;
};

const multiplication = (firstNum, secondNum) => {
  return firstNum * secondNum;
};

console.log(
  performMath(
    (a, b) => {
      return a / b;
    },
    15,
    3
  )
);
```

These functions have only a single line of code that returns something. In a simple common case like this, you can simplify how you define the arrow function to be like this:

```javascript
const addition = (firstNum, secondNum) => firstNum + secondNum;
const subtraction = (firstNum, secondNum) => firstNum - secondNum;
const multiplication = (firstNum, secondNum) => firstNum * secondNum;

console.log(performMath((a, b) => a / b, 15, 3));
```

This is called an _implicit return_. You can see how much simpler our code became.

# Array Iteration Methods

To print all the elements in an array, we learned we can use a `while` or a `for` loop to iterate over the array and print its elements. Those loops are great, but there are more convenient ways of iterating over arrays. There're built-in array methods that allow us to iterate over the elements in an array. They're preferred and easier to use.

## [`.forEach()` Slide](https://docs.google.com/presentation/d/1j9_ilYMYu5nd_VCJiy7t8v_ok3bC6qTvwqu-B3l4C3M/edit#slide=id.g4533db2398_0_81)

## `.forEach()`

Here's the syntax for it:

```javascript
someArray.forEach((arrayElement) => {
  CODE;
});
```

Let's use it to re-write a `for` loop:

```javascript
const colors = ["Royal Blue", "Azure", "Crimson", "Scarlet"];

console.log("Here are some of my favorite colors: ");
for (let i = 0; i < colors.length; i++) {
  console.log(colors[i]);
}

// You can rewrite the loop using the .forEach method:
colors.forEach((color) => console.log(color));
```

## [`.map()` Slide](https://docs.google.com/presentation/d/1j9_ilYMYu5nd_VCJiy7t8v_ok3bC6qTvwqu-B3l4C3M/edit#slide=id.g4533db2398_0_105)

## `.map()`

The `.map()` returns the resulting array of the elements that the function returns. It has the exact same syntax as the `.forEach()` iteration method. Let's use it to re-write a loop:

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let squares = [];

for (let i = 0; i < numbers.length; i++) {
  squares.push(numbers[i] * numbers[i]);
}

// You can rewrite the loop using the .map method:
squares = numbers.map((number) => number * number);
```

## [`.filter()` Slide](https://docs.google.com/presentation/d/1j9_ilYMYu5nd_VCJiy7t8v_ok3bC6qTvwqu-B3l4C3M/edit#slide=id.g4533db2398_0_148)

## `.filter()`

Has the same syntax exactly as the previous two iteration methods. This one returns the resulting array of the elements on which the passed function returns `true`. Let's use it to re-write a loop:

```javascript
const numbers = [1, 2, 3, 4, 5, 11, 12, 15, 17, 18, 19, 21, 22, 23, 34, 56, 78];

let multiplesOfThree = [];

for (let i = 0; i < numbers.length; i++) {
  if (numbers[i] % 3 === 0) {
    multiplesOfThree.push(numbers[i]);
  }
}

// You can rewrite the loop using the .filter method:
multiplesOfThree = numbers.filter((num) => num % 3 === 0);
```
