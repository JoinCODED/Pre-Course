### Topics to discuss:

- What is programming?
- A basic understanding of programming
- Variables in JavaScript
- String concatenation & Template Literals

[Slides](https://docs.google.com/presentation/d/1M83Fc6cOUwKglqaLR02XVjVhyNppJHMxqHFx5K1D0Jk/edit?usp=sharing)

# What is programming?

Programming is using many **predefined commands** that the computer understands, similar to the single-line commands we used in the **Terminal**, and putting them together in a _text file_.

All the applications we'll build will be collections of _text files_ with many lines of these **predefined commands**.

# Introduction To `JavaScript`

We'll learn to build web and mobile apps using the programming language `JavaScript`. But, before we start building the apps, in the Foundations phase we'll learn the basics of `JavaScript`.

During this period, you'll write your code in a file with the `.js` extension, and will see the result of the program in the _console_.

In VS Code, you can open the **Terminal** by pressing `CMD` (or `CTRL` on Windows) and `` ` `` _(ex: CMD/CTRL + `` ` ``)_. Or on the menu: `Terminal` > `New Terminal`. We'll use this **Terminal** to run our code and see the result. This **Terminal** will display the console when we run our `JavaScript` code.

## Brief History of `JavaScript`

`JavaScript` was created in the mid-90's. It's created to build **interactive web pages**. But, since then **JS** is used almost everywhere, even where there isn't a browser. It's given a name resembling "Java" to ride Java's popularity when it was first created. But, Java is to `JavaScript` what car is to carpet. There's no relation whatsoever.

## Programming Basics

Let's start off writing a line of code (a statement) to print a simple message to the console:

```javascript
console.log("Hello World!");
```

The `console.log` part is a **predefined command** in the `JavaScript` language. We can use it to **print** a message to the **console**. The bit in the quotation marks `" "` is a data type called a **_string_**. Which the computer treats as just normal text. So in these quotation marks, you can write any normal text you'd like, and it'll be displayed in the **console** because of the `console.log` part.

This line of code will display the words "`Hello World!`" to the console.

You can also write multiple lines of code. Like this:

```javascript
console.log("Hello World!");
console.log("Welcome to programming!");
```

The program will execute these lines one by one, starting from the top. So the code will display on the following output in the **console**:

```bash
Hello World!
Welcome to programming!
```

#### More on `console.log`

We're not limited to text when printing to **console**. There's other data types, such as integers:

```javascript
console.log(5);
```

To expand on that, you can perform math:

```javascript
console.log(5 + 3); // 8
```

And more...

### Variables

Let's expand this further. Let's say I am printing the following messages:

```javascript
console.log("The GitHub username is TheMshary.");
console.log("TheMshary has 30 repositories.");
```

You can see that the username "`TheMshary`" is repeated multiple times here. What if I want to change my username? I have to re-write this change everywhere the username is repeated. This can be made simpler by storing the username in one place, and re-using it. So we'll use something called a **_variable_** to store the username.

### Discuss `let` Variables Slides

Here's what the code looks like:

```javascript
let username = "TheMshary";

console.log("The GitHub username is " + username);
console.log(username + " has 30 repositories.");
```

The output will be:

```bash
The GitHub username is TheMshary
TheMshary has 30 repositories.
```

Neat, huh? This is how you can concatenate a string with a variable. But, there's another way, which we prefer much more. It's called _Template Literals_ (fancy name, I know,) using these backticks `` ` ` `` instead of quotation marks `" "`:

```javascript
let username = "TheMshary";

console.log(`The GitHub username is ${username}`);
console.log(`${username} has 30 repositories.`);
```

In these backticks, you can type `${ }` and in between the curly brackets you can type in the name of the variable, as we did. The output of this code will be the same:

```bash
The GitHub username is TheMshary
TheMshary has 30 repositories.
```

You can define multiple variables, you're not limited to just one variable in your code.

```javascript
let username = "TheMshary";
let numberOfRepositories = 30;

console.log(`The GitHub username is ${username}`);
console.log(`${username} has ${numberOfRepositories} repositories.`);
```

### Modifying The Variable

It's called a "variable" for a reason: you can change its value. Here's an example of how to do that:

```javascript
let username = "TheMshary";
let numberOfRepositories = 30;

console.log(`The GitHub username is ${username}.`);
console.log(`${username} has ${numberOfRepositories} repositories.`);

username = "Lailz";

console.log(`The new GitHub username is ${username}.`);
console.log(`${username} has ${numberOfRepositories} repositories.`);
```

The output of this will be:

```bash
The GitHub username is TheMshary
TheMshary has 30 repositories.
The GitHub username is Lailz
Lailz has 30 repositories.
```

The code will define the variable `username` with the value `"TheMshary"`, then print the two messages. Then change the value of `username` to `"Lailz"`, then print the two messages with the username changed.

### `JavaScript` Inside Template Literal

Since Lailz always has one more repository than I do, we can **perform math** _inside the Template Literal_:

```javascript
[...]

username = "Lailz";

console.log(`The new GitHub username is ${username}.`);
console.log(`${username} has ${numberOfRepositories + 1} repositories.`);
```

The output of this will be:

```bash
The GitHub username is TheMshary
TheMshary has 30 repositories.
The GitHub username is Lailz
Lailz has 31 repositories.
```

### Constants (`const`)

There's another way to store a value, using `const`.

#### Discuss `const` Slides

Here's the same example using `const` instead of `let`:

```javascript
const username = "TheMshary";

console.log(`The GitHub username is ${username}.`);
console.log(`${username} has 30 repositories.`);

// username = "Lailz";
// console.log(`The new GitHub username is ${username}.`);
// console.log(`${username} has 31 repositories.`);
```

Works the same. However, using `const` means you can't change the value later on. So if we try to...

```javascript
const username = "TheMshary";

console.log(`The GitHub username is ${username}.`);
console.log(`${username} has 30 repositories.`);

username = "Lailz"; // goes kaboom
console.log(`The new GitHub username is ${username}.`);
console.log(`${username} has 31 repositories.`);
```

...the program will crash. Sad music: ON.
