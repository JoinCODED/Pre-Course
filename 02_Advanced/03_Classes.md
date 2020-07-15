### Topics to discuss:

- Classes
- Inheritance
- Overriding Methods

[Slides](https://docs.google.com/presentation/d/13K5VLKXDYfUcoiCSiYLkUl8vo_DpCxaL0EepePHQ9Tw/edit?usp=sharing)

# Classes Intuition

Continuing the scenario of having instructors, let's say we have the following instructor objects:

```javascript
const instructorMshary = {
  name: "Mshary",
  interests: ["Meditation", "Terrible Coffee"],
  topics: ["JavaScript", "React"],
};
const instructorLaila = {
  name: "Laila",
  interests: ["Fantasy Novels", "Nightowl-ing"],
  topics: ["JavaScript", "React", "React Native", "Express"],
};
const instructorAziz = {
  name: "Aziz",
  interests: ["Attack On Titan", "Board Games"],
  topics: ["JavaScript", "React", "React Native", "Express"],
};
```

The problem with this is that you're repeating yourself. The keys in the objects are being repeated for every single object. You might make mistakes by mispelling a key for example. It also takes a lot of extra time. In this example it's only two keys, but in reality your data will be way more complex than this.

With classes, we can define the _structure_ of an instructor. We can say that an instructor has a name and an array of interests. Then when we want to create a new instructor, we just make a new instructor and pass it the name and array of interests. We don't have to redefine the structure everytime.

## Slides: Blueprint for Objects

## Introducing Classes

Here's a class representing a single instructor:

```javascript
class Instructor {
  name = "Mshary";
  interests = ["Meditation", "Terrible Coffee"];
  topics = ["JavaScript", "React"];
}

const instructor = new Instructor();
console.log(instructor); // Instructor { name: 'Mshary', ... }
```

Here we used the `new` keyword that creates an _instance_ of the `Instructor` class. This _instance_ is an object, like the objects we had before we defined the class.

Note thought that a class's name is always _singular_ and starts with a capital letter.

You can define a function inside the class (a method):

```javascript
class Instructor {
  name = "Mshary";
  interests = ["Meditation", "Terrible Coffee"];
  topics = ["JavaScript", "React"];

  sayHello = () => console.log(`Hi, I'm ${this.name}`);
}

const instructor = new Instructor();
instructor.sayHello(); // Hi, I'm Mshary
```

Notice how we're calling this function. We're using the same dot notation `.` as we did back with arrays and objects. That's because this is a method defined only for instructors (instances of the `Instructor` class).

Also notice in the `sayHello()` method inside the class, to access an object's name attribute, the same object that we're calling this method under, we wrote `this.name`. `this` refers to the object itself. The value of `this` depends on which object we're using. More on `this` later.

## Reusability

We still didn't solve the problem. How do we use the same class to create multiple different instructors with different names and attributes?

We still didn't solve the problem. How do we use the same class to create multiple different instructors with different names and attributes?

We can do that by using a `constructor()` method inside the `Instructor` class:

```javascript
class Instructor {
  constructor(firstName, lastName, interests, topics) {
    this.name = `${firstName} ${lastName}`;
    this.interests = interests;
    this.topics = topics;
  }

  sayHello = () => console.log(`Hi, I'm ${this.name}`);
}
```

Now to create a new instructor:

```javascript
const instructorMshary = new Instructor(
  "Mshary",
  "AlSharekh",
  ["Meditation", "Terrible Coffee"],
  ["JavaScript", "React"]
);
instructorMshary.sayHello(); // Hi, I'm Mshary AlSharekh
```

We can now create more instructors without re-writing the structure of an instructor:

```javascript
const instructorMshary = new Instructor(
  "Mshary",
  "AlSharekh",
  ["Meditation", "Terrible Coffee"],
  ["JavaScript", "React"]
);
const instructorLaila = new Instructor(
  "Laila",
  "AlKandery",
  ["Fantasy Novels", "Nightowl-ing"],
  ["JavaScript", "React", "React Native", "Express"]
);
const instructorAziz = new Instructor(
  "Aziz",
  "AlWhistler",
  ["Attack On Titan", "Board Games"],
  ["JavaScript", "React", "React Native", "Express"]
);

instructorMshary.sayHello(); // Hi, I'm Mshary AlSharekh
instructorLaila.sayHello(); // Hi, I'm Laila AlKandery
instructorAziz.sayHello(); // Hi, I'm Aziz AlWhistler
```

You see how we defined the structure and property names only once (in the class) and used it for multiple different instructors? This is one of the things you can do with classes.

The value of `this.name` in the `sayHello()` method when calling `instructorMshary.sayHello()` will be `"Mshary AlSharekh"`. But the value of `this.name` when calling `instructorLaila.sayHello()` will be `"Laila AlKandery"`. So `this` always refers to the object itself.

# Inheritance

## Slides: Inheritance

Inheritance takes your classes game to the next level. You can construct more elaborate data structures with inheritance. In reality, an instructor is a _person_ right? Whatever a person has, an instructor also has. So we can take everything that's common between all persons and put that in a separate `Person` class:

```javascript
class Person {
  constructor(firstName, lastName, interests) {
    this.name = `${firstName} ${lastName}`;
    this.interests = interests;
  }

  sayHello = () => console.log(`Hi, I'm ${this.name}`);
}
```

Then define the instructor class with attributes that only instructors have:

```javascript
class Instructor extends Person {
  constructor(firstName, lastName, interests, topics) {
    super(firstName, lastName, interests);
    this.topics = topics;
  }
}
```

Notice the `extends Person` bit. That's the part that faciliates the inheritance between the two classes. In this example, the `Person` class is the _parent_ class, and the `Instructor` is the _child_ class.

With this inheritance facilitated, an instructor can use methods defined under the `Person` class, same as before.

## Overriding Methods

Instructors may have a unique greeting that normal persons don't do. We can _override_ the `Instructor`'s `sayHello()` method:

```javascript
class Instructor extends Person {
  constructor(firstName, lastName, interests, topics, greeting = "Hello") {
    super(firstName, lastName, interests);
    this.topics = topics;
    this.greeting = greeting;
  }

  sayHello = () =>
    console.log(
      `${this.greeting}, my name is ${this.name}, and I teach ${this.topics[0]}, and more!`
    );
}

const person = new Person("Michael", "Singer", [
  "Writing Books",
  "Building Billion-Dollar Businesses",
  "Meditation",
]);
person.sayHello(); // Hi, I'm Michael Singer.

const instructorMshary = new Instructor(
  "Mshary",
  "AlSharekh",
  ["Meditation", "Terrible Coffee"],
  ["JavaScript", "React"],
  "Hey"
);
instructorMshary.sayHello(); // Hey, my name is Mshary AlSharekh, and I teach JavaScript, and more!
```

Try removing `"Hey"` from `instructorMshary`.
