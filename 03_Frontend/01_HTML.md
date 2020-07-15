## Discussion

### Topics to discuss:

- HTML basics
- HTML Attributes
- CSS basics

[HTML tags](https://www.w3schools.com/tags/ref_byfunc.asp)

[CSS properties](https://www.w3schools.com/cssref/)

[Google Chrome download](https://www.google.com/chrome/)

[Anatomy of a CSS ruleset](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics#Anatomy_of_a_CSS_ruleset)

# HTML

## Introduction to HTML

HTML, short for HyperText Markup Language, is the language used to build webpages. Every webpage on the internet uses this language, from Facebook to Google, to reddit to YouTube.

Technically, HTML is not a programming language, it's a _markup language_. The difference is technical and isn't important today.

## HTML Document Structure

HTML files are denoted with the `.html` extension. Every HTML document consists of a certain skeletal structure:

```html
<!DOCTYPE html>
<html>
  <head>
    [...]
  </head>
  <body>
    [...]
  </body>
</html>
```

Those things that start with a `<` and end with a `>` are called HTML **_tags_**. They usually come in pairs: an opening tag and a closing tag. The two tags make up an HTML _element_. These elements are the building blocks used to construct a webpage, as you'll see. They usually consist of an _opening tag_ and a _closing tag_. Let's take the `<head>` element, for example. The opening tag is `<head>`, it's corresponding _closing tag_ is `</head>`. The closing tags have a `/` after the `<`.

With this skeletal structure, nothing will appear on the webpage. Any content you want to display on the webpage should be written in HTML inside the `<body>` tag.

---

## Task

(10 minutes.)

In this task, you'll be building your own portfolio page!

1. Create a folder inside `Development` called `Portfolio`.
2. Open the `Portfolio` directory in VS Code.
3. Create a new file called `index.html`.
4. Write the HTML skeletal structure in `index.html`.

---

## Headings

There's many built-in HTML elements you can use to display various types of content on the page. The first we'll get into is heading tags:

```html
<h1>Mshary</h1>
```

This is an HTML tag that displays a large heading text. The text you write between the opening and closing tags (inside the element) is what will be displayed on the screen.

There's other heading elements. From `<h1>` to `<h6>`. `<h1>` is the largest, and `<h6>` is the smallest.

([More on `<h1>`](https://www.w3schools.com/tags/tag_hn.asp))

## Paragraphs

To display a paragraph of text, you can use the `p` element:

```html
<p>You can contact me at: mshary@joincoded.com</p>
<p>My GitHub: TheMshary</p>
```

This works as you'd expect, it displays a paragraph of text.

([More on `<p>`](https://www.w3schools.com/tags/tag_p.asp))

## Unordered Lists and List Items

You can also display a _list_ using the `<ul>` and `<li>` elements. Here's an example:

```html
<h2>Songs</h2>
<ul>
  <li>"Killing Me Softly" by Frank Sinatra</li>
  <li>"As Time Goes By" by Seth MacFarlane</li>
  <li>"Helium" by Sia</li>
</ul>
```

The `<ul>` element denotes that inside there's a an **u**nordered **l**ist. You denote a **l**ist **i**tem with the `<li>` element. This HTML code displays a bullet list with three list items.

([More on `<ul>`](https://www.w3schools.com/tags/tag_ul.asp))

([More on `<li>`](https://www.w3schools.com/tags/tag_li.asp))

## Ordered Lists

You can display an **o**rdered **l**ist as well using the `<ol>` element.

```html
<h2>Books</h2>
<ol>
  <li>"A Knight Of The Seven Kingdoms" by George R. R. Martin</li>
  <li>"The Untethered Soul" by Michael Singer</li>
  <li>"How To Fight A Hydra" by Josh Kaufman</li>
</ol>
```

This works the same as the `<ul>` element, but it's a numbered list.

([More on `<ol>`](https://www.w3schools.com/tags/tag_ol.asp))

## Images

You can display an image as well using the `<img>` element.

```html
<img
  src="https://thefocuscourse.com/wp-content/uploads/2019/12/fight-a-hydra.jpg"
/>
```

This element requires you give it the `src` attribute so it knows what image to display.

([More on `<img>`](https://www.w3schools.com/tags/tag_img.asp))

## Tab Title

You can customize the text that displays on the tab in the window when you open the webpage. Right now, it says "index.html":

![index.html tab title](https://i.imgur.com/mn2rSLB.png)

You can change that with the `<title>` tag in the `<head>` element:

```html
<head>
  <link href="styles.css" rel="stylesheet" type="text/css" />
  <title>Mshary's Portfolio</title>
</head>
```

Now it looks like this:

![index.html tab title edited](https://i.imgur.com/u5YGVlw.png)

---

## Task (Cont.)

(20 minutes.)

Continuing on the previous task...

1. Create an `<h1>` heading to display your name.
2. Using one or more `<p>` tag(s), give a brief description of who you are.
3. Create an `<h2>` heading titled "Interests".
4. Under this heading, display an **u**nordered **l**ist of some of your interests.
5. Create another `<h2>` heading titled "Hobbies".
6. Under this heading, display an **o**rdered **l**ist of some of your hobbies.
7. Under the "Hobbies" ordered list, use the `<img />` tag to display an image that represents one of your hobbies.

---

## HTML Attributes

You can display the numbered list using letters instead of numbers using an HTML attribute.

```html
<h2>Books</h2>
<ol type="A">
  <li>"A Knight Of The Seven Kingdoms" by George R. R. Martin</li>
  <li>"The Surrender Experiment" by Michael Singer</li>
  <li>"How To Fight A Hydra" by Josh Kaufman</li>
</ol>
```

In HTML you can customize certain things about how an HTML element is displayed by defining _attributes_. Attributes are options used to customize the element. They are defined inside the opening tag. In this example, `type` is an attribute we defined and we gave it the value `A`. This is how this tag works, it reads an attribute called `type`, and depending on its value will display the list differently.

Another attribute you may use is `width` to specify the width of an image:

```html
<img
  src="https://thefocuscourse.com/wp-content/uploads/2019/12/fight-a-hydra.jpg"
  width="400px"
/>
```

This is an attribute that works on images to set the width of this image on the screen to _400 pixels_.

## Styling You can customize how content in displayed by applying the

`style` attribute to an HTML element. Here's an example of how we're changing
the color of the `

<h1>
  ` text to red: ```html
  <h1 style="color: red;">Mshary</h1>
</h1>
````

You can also change the font of the text:

```html
<h1 style="color: red; font-family: monospace;">Mshary</h1>
```

There's a lot more we can do with styling. We'll learn more about that soon.

Writing all our page's styling within the HTML code like this quickly gets messy and difficult to manage and maintain. There's a better way...

