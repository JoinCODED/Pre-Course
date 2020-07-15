### Topics to discuss:

- Objects
- Dot notation
- Bracket notation

# Objects

There's even more stuff? We already know variables, functions, functions without names, arrow functions, loops, array iteration methods, if-statements, and the pythagoras theorem and why plants are green. Do we need to learn about objects?

Well.... yes. You'll see why, trust me.

Let's say you have the following data on a single real-life person:

```javascript
const name = "Mshary";
const age = 25;
const interests = ["Art", "Humanities", "History", "Meditation", "Anime"];
```

These data points aren't connected in any way. They're separate variables. There's nothing here in the code that indicates that these are about the same person in real life. We can use an array to group them together, but the only way to access elements in an array is using index, which doesn't tell you what data point you're accessing, whether it's the name or age or whatever.

So objects come in to help with this. Here's the syntax for objects:

```javascript
const varName = {
  keyOne: ValueOne,
  keyTwo: ValueTwo,
  [...]
}
```

Objects consist of key/value pairs. These key/value pairs are knows as "`properties`". Each `key` corresponds to a `value`.

Here's an object that represents a real-life person:

```javascript
const person = {
  name: "Mshary",
  age: 25,
  interests: ["Art", "Humanities", "History", "Meditation", "Anime"],
};
```

You can expand on that and have an object inside an object:

```javascript
const person = {
  name: "Mshary",
  age: 25,
  interests: ["Art", "Humanities", "History", "Meditation", "Anime"],
  githubAccount: {
    username: "TheMshary",
    numberOfRepos: 1000,
  },
};
```

# Using Objects

## Dot Notation

So how do we access a value, such as the name, of an object? You can use the dot notation and type the corresponding key. Here's an example:

```javascript
console.log(person.name); // "Mshary"
// You can access the entire array and then access elements inside as normal
console.log(person.interests[2]); // "History"
// If it's nested, keep nesting the dots.
console.log(person.githubAccount.username); // "TheMshary"
```

You can use the dot notation to also modify any values:

```javascript
person.age = 26; // 2021
```

## Adding New Properties

You're not limited to only the properties you define when you create the object; you can add new properties later on. You can add a person's music:

```javascript
person.music = [
  "Book Of Love by Peter Gabriel",
  "Every Breaking Wave by U2",
  "Fly Me To The Moon by Frank Sinatra",
];
```

## Bracket Notation

Using brackets `[]` you can type the key as a string to get the value, like this:

```javascript
console.log(person["name"]); // Mshary
```

Dot notation is always preferred, but there are reasons to use bracket notation sometimes, like:

- If the key is a string with spaces
- If you don't know the key in advance. Example:

  ```javascript
  const someObj = {
    "shade of blue": "Aqua",
    "midnight sun": "rising",
  };

  const keyName = "midnight sun";

  console.log(someObj[keyName]);
  console.log(someObj["shade of blue"]);
  ```

# Game of Thrones Example

Another example we can use to encompass all those topics on objects is themed around Game of Thrones (don't worry, no spoilers ahead):

```javascript
const gameOfThrones = {
  seasons: 8,
  goodSeasons: 6,
  houses: {
    lannister: ["Tywin", "Cercei", "Jamie", "Tyrion"],
    stark: [
      "Eddard",
      "Lyanna",
      "Catelyn",
      "Robb",
      "Sansa",
      "Rickon",
      "Bran",
      "Arya",
    ],
  },
};
```

Here we have the four most powerful houses in Westeros (fictional continent in the Game of Thrones universe), and some other data on GoT, including the names of the members of two of those families.

Let's imagine we're writing a program for our users to pick their favorite house and they see the names of the members of that house. So we have a variables containing their favorite house, House Lannister:

```javascript
const favoriteHouse = "lannister";
```

To display the list of names of that house:

```javascript
console.log(
  `The members of your favorite house are: ${gameOfThrones.houses[favoriteHouse]}`
);
```
