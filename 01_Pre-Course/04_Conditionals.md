# Conditional Statements

## Discussion

### Topics to discuss:

- Boolean values
- Boolean comparisons
- `if`-statement
- Logical Operators

[Slides](https://docs.google.com/presentation/d/1M83Fc6cOUwKglqaLR02XVjVhyNppJHMxqHFx5K1D0Jk/edit?usp=sharing)

# Booleans

We've seen data types like `strings` and `integers`. There's more, like _booleans_. **`Boolean`** values are either **true** or **false**. Here's an example:

```javascript
console.log(true);
console.log(false);
```

`true` is something that is _true_, and `false` is something that isn't _true_. You can compare numbers and get back either true or false, depending on the comparison:

```javascript
console.log(5 > 3); // true
console.log(5 === 3); // false
```

We understand that 5 is greater than 3, so `5 > 3` evaluates to `true`. And 5 isn't equal to 3, so `5 === 3` evaluates to false.

# `if`-statement

We know that the code executes **line by line from the top**. What if you want to do something different depending on a certain condition? Well, we have a **built-in command** called an `if`-statement.

## [Conditional Statement Slide](https://docs.google.com/presentation/d/1P8MPXUktK_viz0AO2Vqu4WKPrCiWLh7CGbiKrTztLcU/edit#slide=id.g44b02ef8a3_0_213)

Here's the syntax for it:

```javascript
if (CONDITION) {
  CODE;
}
```

The `CODE` inside will only run if the `CONDITION` evaluates to `true`. If it's false, the code inside won't run. Here's an example:

```javascript
const x = 5;
const y = 3;

if (x > y) {
  console.log("Math works!");
}
```

Because `x > y` will evaluate to `true`, the `console.log` inside will run.

You can write as many lines of code inside the `if`-statements as you need to:

```javascript
const x = 5;
const y = 3;

if (x > y) {
  console.log("Math works!");
  console.log(`${x} + ${y} = ${x + y}`);
}
```

Output:

```bash
Math Works!
5 + 3 = 8
```

There's more... You can also run some code if the condition _isn't_ met. Let's change the values for `x` and `y` and show an example:

```javascript
const x = 10;
const y = 28;

// x > y will now evaluate to false.

if (x > y) {
  console.log("Math Works!");
} else {
  console.log("Where did Math go?");
}
```

The output will be:

```bash
Where did Math go?
```

The `if`-statement is meant to be as **logical** as possible. You can read it like this:

```
If x is greater than y print "Math Works!", if it's not then print "Where did Math go?"
```

You can also expand the condition to be a **series of conditions**. Here's an example of two conditions, and an `else`:

```javascript
if (x < y) {
  console.log("Math Works!");
} else if (x > y) {
  console.log("Math works?");
} else {
  console.log("Where did Math go?");
}
```

You can keep chaining these `if`-statements as many times as you need to.

> Here's a tip: if the code inside the `if`-statement is only a single line of code, like in our example here, you can remove the curly braces:

```javascript
if (x < y) console.log("Math Works!");
else if (x > y) console.log("Math works?");
else console.log("Where did our math go?");
```

Here's a more meaningful usage of the if-statement:

```javascript
const age = 5;

if (age > 12) console.log("Welcome aboard!");
else console.log("Sorry, age restricted area. Come back when you're older.");
```

# Logical Operators

## Intuition

Let's say you meet **Michael**, who is **35** years old. If he says to you "My name is Michael **_and_** I'm 35 years old." Is he lying? ...No he's telling the truth. Both of the things he said, his name being **Michael** and his age being **35**, are both _true_.

What if he says "My name is Michael **_and_** I'm 20 years old." ...He's lying. Even though his name is actually **Michael**, his age isn't **20**. The first thing he said is _true_, but the second is _false_. So you can think of what he said logically as `true and false`. Which we now know evaluates to `false`.

Now what if he says "My name is Michael **_or_** I'm 20 years old." ...Now he's telling the truth. He actually is either named **Michael** or is **20** years old. Logically: `true or false` evaluates to `true`.

One more...

If he says "My name is Michael **_and_** I'm **_not_** 20 years old." True or false? ...True. Logically: `true and not false` evaluates to `true and true` which evaluates to `true`.

This is logical operators with boolean values in coding. Here's an example:

```javascript
const age = 25;
const doneFiveCrazyThings = true;

// "age is less than 40 and have not done five crazy things"
if (age < 40 && !doneFiveCrazyThings) console.log("DO RISKY STUFF, MAYBE.");
```

The `&&` is how you write a logical `and` in `JavaScript`, and the `!` is how you write the logical `not` in `JavaScript`. So you can read this condition like so:

```
If age is less than forty and has not done five crazy things, then print "DO RISKY STUFF, MAYBE."
```

Here's a list of logical operators in `JavaScript`:

```
- and `&&`
- or `||`
- not `!`
```

Lastly, there's one more commonly used **mathematical operator**, the `mod` or `modulo`, denoted by `%`. Here's an example:

```javascript
console.log(7 % 2); // 1
console.log(8 % 2); // 0
```

`7 % 2` will divide `7` by `2` and return the **remainder** of the **division**, which will be `1`. Here's another example:

```javascript
const number = 5;

if (number % 2 === 0) console.log("EVEN");
else console.log("ODD");
```
