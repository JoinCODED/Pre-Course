# Arrays and Loops

## Discussion

### Topics to discuss:

- Arrays
- Array Methods
- Loops (`while` and `for`)

[Slides](https://docs.google.com/presentation/d/1dkovfExxp06AMyyvZ2Vr5i4H6CuDikzGNVZrzUMsOwk/edit?usp=sharing)

[`const` vs `let` vs `var` in JavaScript](https://medium.com/javascript-scene/javascript-es6-var-let-or-const-ba58b8dcde75)

# Array Basics

## [Array Slide](https://docs.google.com/presentation/d/1dkovfExxp06AMyyvZ2Vr5i4H6CuDikzGNVZrzUMsOwk/edit#slide=id.g453392c2a0_0_18)

What is an **array**? Why do we need more stuff? We already have _variables_ and _functions_. For this lesson, we'll use a scenario that'll help explain these concepts. Let's say you're writing a progam that **stores** the `instructors` you have. So you create the following _variables_ for each instructor:

```javascript
const instructorMshary = "Mshary";
const instructorLaila = "Laila";
const instructorAziz = "Aziz";
```

But, they're **not stored in a central location** that connects the _variables_. If you want to **print** the number of `instructors` you have, you have to look at the code and manually count the _variables_. If you have a new instructor, you have to create a new _variables_ for them, and manually increase the count of `instructors` you have. It's not dynamic, it's very problematic.

You can link them together by putting the instructor names in an _array_ of `instructors`:

```javascript
const instructors = ["Mshary", "Laila", "Aziz"];
```

The array is denoted by the square brackets `[]`. How do you access the values in the array (called "elements")?

```javascript
const instructors = ["Mshary", "Laila", "Aziz"];

console.log(instructors[0]); // Mshary
console.log(instructors[1]); // Laila
console.log(instructors[2]); // Aziz
```

You can use the square brackets `[]` to access elements inside the array. The number you enter inside the brackets is called the **_index_**. Notice that we're accessing `"Mshary"`, the _first_ element, by entering `0`. The index of elements in an array _always starts with 0_ in `JavaScript` and most programming languages.

You can modify a value in the array like this:

```javascript
instructors[0] = "Mishmish";
console.log(instructors[0]); // Mishmish
```

So all of this is good, but we still have to manually count the number of `instructors` in the array. How can we use arrays to dynamically tell us the number of `instructors` we have? Stick around to find out ;)

# More on Arrays

So far we covered the basic usage of an array in `JavaScript`. But, you can do more through using the built-in array methods and attributes. You can use a built-in array attribute that tells you how many elements there are in the array:

```javascript
console.log(instructors.length); // 3
```

The `.` here indicates that we're accessing something in the array. In this case, we're accessing an attribute called `length`, which gives us the _length_ of the array.

You can also use a built-in array method to add new elements to the array:

```javascript
instructors.push("Khalid");

console.log(instructors.length); // 4

// instructors: ["Mishmish", "Laila", "Aziz", "Khalid"]
```

`.push()` is a **function** like any other, but it only works on arrays.

Another **function** allows you to get a subset of the array elements:

```javascript
console.log(instructors.slice(0, 2)); // ["Mishmish", "Laila"]
```

You give it two numbers, say `0` and `2`. You'll get back an array of the elements from index `0` (inclusive) to index `2` (exclusive). This means that the element at index `2` will not be included in the resulting array you're getting back.

You can use a negative index with `.slice()`. Let's say you want all the elements except the last one, here's how:

```javascript
console.log(instructors.slice(0, -1)); // ["Mishmish", "Laila", "Aziz"]
```

The `-1` means go back one from the end of the array. To get all elements except that last two:

```javascript
console.log(instructors.slice(0, -2)); // ["Mishmish", "Laila"]
```

---

## Quizzes

What will the following **print**?

```javascript
console.log(instructors.slice(1, -1));
```

Second quiz:

```javascript
// QUIZ:
//                      ["Aziz", "Khalid"]  <-- how do i get this...
// ["Mishmish", "Laila", "Aziz", "Khalid"]  <-- ...from this?
```

Answer:

```javascript
instructors.slice(-2, instructors.length);
```

---

# Loops

## [`while` Loop Slide](https://docs.google.com/presentation/d/1dkovfExxp06AMyyvZ2Vr5i4H6CuDikzGNVZrzUMsOwk/edit#slide=id.g44b077e4f9_0_15)

With loops, you can do something special: You can repeat some code or series of operations multiple times without rewriting the code. Here's the syntax:

```javascript
while (CONDITION) {
  CODE;
}
```

Similar to the `if`-statement, there's a `CONDITION` that if evaluated to `true`, the block of code between the curly brackets `{}` will be executed. Once it's done executing the block of code, it'll then check the `CONDITION` again and see if it evaluates to `true` again. If it does, it'll execute the `CODE` once again, and continues on like this until the `CONDITION` evaluates to `false`. Then it'll exit the loop.

Here's a simple example using a `while` loop:

```javascript
let count = 0;
while (count < 5) {
  console.log(count);
  count++;
}
```

Output:

```
0
1
2
3
4
```

---

## Quiz

What is the **output** of the following loop:

```javascript
let count = 0;
while (count < 7) {
  console.log(count);
}
```

Answer: Infinite loop.

---

We can use loops to iterate over an array. Here's an example where we iterate over the names of `instructors` we have and have them all introduce themselves:

```javascript
let i = 0;
while (i < instructors.length) {
  console.log(`Hello, I'm ${instructors[i]}`);
  i++;
}
```

`i` goes from `0` to the length of the `instructors` array. With each iteration the value of `i` increases by 1. So with each iteration, we access another element from the array.

Output:

```
Hello, I'm Mishmish
Hello, I'm Laila
Hello, I'm Aziz
Hello, I'm Khalid
```

## [`for` Loop Slide](https://docs.google.com/presentation/d/1dkovfExxp06AMyyvZ2Vr5i4H6CuDikzGNVZrzUMsOwk/edit#slide=id.g44b077e4f9_0_22)

## `for` loop

The kind of `while` loop we just saw, where you have a counter that starts somewhere, is compared with another number, and is incremented at the end of the loop, usually used to iterate over an array, is so commonly used that they made another loop, the `for` loop, that works for that exact purpose. Here's the same loop re-written as a `for`-loop:

```javascript
for (let i = 0; i < instructors.length; i++) {
  console.log(`Hello, I'm ${instructors[i]}`);
}
```

The `for`-loop is a more specific version of the `while` loop.
