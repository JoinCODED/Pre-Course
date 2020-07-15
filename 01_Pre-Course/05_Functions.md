# Functions

## Discussion

### Topics to discuss:

- Functions in JavaScript
- `return`
- Function parameters

[Slides](https://docs.google.com/presentation/d/1M83Fc6cOUwKglqaLR02XVjVhyNppJHMxqHFx5K1D0Jk/edit?usp=sharing)

# Functions

## [Function Slide](https://docs.google.com/presentation/d/1P8MPXUktK_viz0AO2Vqu4WKPrCiWLh7CGbiKrTztLcU/edit#slide=id.g78355d9c21_0_0)

## Function Basics

You can think of a **function** as a **block of code with a name**. You can run that **block of code** by typing the **name**, this way you can write the code **once** and **reuse it** multiple times.

Here's the syntax of a **function**:

```javascript
function funcName() {
  CODE;
}
```

Here's a simple example, with a single line:

```javascript
function helloWorld() {
  console.log("Hello");
}
```

Now, that we have it **defined**, we can actually _call_ the **function** so that it runs the code inside the **function**'s **block of code**:

```javascript
helloWorld();
```

We can reuse the **function**'s code by calling the **function** as many times as we want:

```javascript
helloWorld();
helloWorld();
helloWorld();
```

## [Function w/ Parameters Slide](https://docs.google.com/presentation/d/1P8MPXUktK_viz0AO2Vqu4WKPrCiWLh7CGbiKrTztLcU/edit#slide=id.g44b02ef8a3_0_220)

## Function w/ Parameters

You can also think of it as an _input_ and _output_. So the **function** with a name can receive _parameters_, then perform some operations, then give back an _output_. Those parantheses `()` are there to receive the _parameters_. Here's an example:

```javascript
function addOne(x) {
  return x + 1;
}
```

In this code, the function receives a parameters: `x`. Parameters are `let` variables, but their value comes from when the function is called, as you'll see next. What's written after the `return` keyword will be returned to where the function was called. Here's how you'd use such a function:

```javascript
const result = addOne(7);
console.log(result); // 8
```

How this'll work is that the parameter `x` will be assigned the value `7`, because when calling the function we put the number `7` between the parantheses `(` `)`. Then the `addOne()` function will add `1` to the number resulting in `8`, then the number `8` will be _`return`ed_.

When the number `8` is _`return`ed_, the code will evaluate to this:

```javascript
const result = 8;
console.log(result); // 8
```

Here's another example with two parameters:

```javascript
function add(a, b) {
  const result = a + b;
  return result;
}
```

This function receives two parameters: `a` and `b`. Here's how you'd use this function:

```javascript
const result = add(4, 7);
console.log(result); // 11
```

How this'll work is that the parameter `a` will be assigned the value `4`, because when calling the function we put the number `4` first, then second is number `7`, which will be assigned to the second parameter `b`. Then the `add()` function will add the two number resulting in `11`, then the number `11` will be _`return`ed_.

When the number `11` is _`return`ed_, the code will evaluate to this:

```javascript
const result = 11;
console.log(result); // 11
```

**_Where you called the function will be replaced with the value it returned._**

## A Bit on Naming Convention

You might notice a convention when naming **functions** and **variables** as we go on. **Functions** are usually _verbs_, because they usually perform a particular task or function (hence why they're called **functions**). So they're usually named as a verb, like our function `add()`, because it performs the task of *add*ing numbers together.

While **variables** are usually _nouns_. Like `result`. Because they're usually named after the data they contain.

## Variable Arguments

Let's expand on this a step further...

The values you pass to a function with _parameters_ can be **variables**:

```javascript
const firstNumber = 15;
const secondNumber: 3;

const result = add(firstNumber, secondNumber);
console.log(result); // 45
```

The **variables** `firstNumber` and `secondNumber` being passed to the `add()` **function** are called _function **arguments**_. While the **variables** _inside_ the function, `a` and `b` are called _function **parameters**_.
