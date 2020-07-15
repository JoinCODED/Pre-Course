### Topics to Discuss

- Bootstrap
- Bootstrap's Grid System
- Bootstraps' Components

[Bootstrap](https://getbootstrap.com/)

[Bootstrap's Grid System](https://getbootstrap.com/docs/4.5/layout/grid/)

[Bootstrap Components](https://getbootstrap.com/docs/4.5/components/alerts/)

# What is Bootstrap?

## Introduction to Bootstrap

Bootstrap is something Twitter built a long time ago in order to have their UI design be consistent across device screen sizes. So it's main power lies in its responsiveness with the screen size. It accomplishes this with their grid system. Bootstrap also comes with pre-built components whose code you can easily copy&paste then customize to fit your needs.

The Bootstrap library consists of a collection of CSS and JS files. It's no magic box.

## Setting Up Bootstrap

To get Bootstrap, you just need to link the Bootstrap code into your HTML file. It'll very efficiently download the code from a CDN (Content Delivery Network) that is setup to very quickly deliver the Bootstrap code to your website. No need to learn how it works. All you need is to get a few lines of HTML code in your HTML document. (You can find the steps on the official website [here](https://getbootstrap.com/docs/4.5/getting-started/introduction/#quick-start)) Place the following line in your `<head>` element:

```html
<link
  rel="stylesheet"
  href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css"
  integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk"
  crossorigin="anonymous"
/>
```

Place the following lines at the bottom of your `<body>` element (just above the closing `</body>` tag):

```html
<script
  src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
  integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
  crossorigin="anonymous"
></script>
<script
  src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
  integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
  crossorigin="anonymous"
></script>
<script
  src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js"
  integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI"
  crossorigin="anonymous"
></script>
```

## Grid System

Bootstrap's grid system works with containers of rows and columns. The grid system doesn't appear on the page, the user doesn't see it. But it helps you organize it. It splits the page into as many rows as you like, and each row consists of 12 columns. This grid system is what makes the UI design consistent across screen sizes.

This grid system also works to realign the elements depending on the screen size. So maybe the layout changes a bit if it's being viewed from a phone than from a laptop for example.

Here's an example of colored columns:

```html
<div class="row">
  <div class="col" style="background-color: red;">
    One of three columns
  </div>
  <div class="col" style="background-color: green;">
    One of three columns
  </div>
  <div class="col" style="background-color: blue;">
    One of three columns
  </div>
</div>
```

Let's take a moment to unpack all the new things we have here...

These `<div>` elements are used to organize and arrange different parts of your webpage. These tags don't display anything on the page at all, they're used to group together different HTML elements that meaningfully display a single "_thing_" on the webpage. So maybe like a person's profile card on the webpage is made up of many HTML elements, can be grouped together into a single `<div>`. `<div>`s are used a ton when getting into even basic web design like we're doing here.

A row in the grid system is any element with the `class` "`row`". A row contains 12 columns in total that span the width of the element that the `row` class is applied to.

The `<div>`s with class "col" are the columns. Notice how these divs are siblings, meaning they're next to each other and are all directly inside the row. Defining them this way will allocate each div the same number of columns as the other divs. So **the total 12 columns will be split evenly across these three `<div>` elements**.

You can assign manually the number of columns you want each div to have, like this:

```html
<div class="row">
  <div class="col-2" style="background-color: red;">
    One of three columns
  </div>
  <div class="col-8" style="background-color: green;">
    One of three columns
  </div>
  <div class="col-2" style="background-color: blue;">
    One of three columns
  </div>
</div>
```

This way, the first and last divs each take the width of 2 out of 12 columns, so they're not as wide as they used to be, and the middle part now takes 8 out of 12 columns, making it take center stage.

This is the core of the grid system. You can expand on it and explore it as much as you'd like to learn more about it.

## More Than 12?

What happens if you create more columns in a single row than 12 columns? Try this code:

```html
<div class="row">
  <div class="col-4" style="background-color: red;">
    One of three columns
  </div>
  <div class="col-4" style="background-color: green;">
    One of three columns
  </div>
  <div class="col-4" style="background-color: blue;">
    One of three columns
  </div>
  <div class="col-4" style="background-color: purple;">
    One of three columns
  </div>
</div>
```

These now add up to 16 columns. What happens is the last div (purple) will go into the next line on the screen, and will be displayed below the first div (red).

## Container

You can add something called a _container_ to a `<div>` that'll contain and center the content of inside the `<div>` element, and also set a fixed width to the page. This fixed width increases if the size of the screen increases over certain breakpoints.

```html
<div class="container">
  <div class="row">
    <div class="col-4" style="background-color: red;">
      One of three columns
    </div>
    <div class="col-4" style="background-color: green;">
      One of three columns
    </div>
    <div class="col-4" style="background-color: blue;">
      One of three columns
    </div>
    <div class="col-4" style="background-color: purple;">
      One of three columns
    </div>
  </div>
</div>
```

Now the content is centered!

## Screen Sizes

You can specify different column arrangements for different screen sizes. Let's say, in this table of colors we have, we want to display _three colors in a row on a laptop screen_ and only _one color in a row on a phone screen_. Here's how:

```html
<div class="container">
  <div class="row">
    <div class="col-md-4 col-sm-12" style="background-color: red;">
      One of three columns
    </div>
    <div class="col-md-4 col-sm-12" style="background-color: green;">
      One of three columns
    </div>
    <div class="col-md-4 col-sm-12" style="background-color: blue;">
      One of three columns
    </div>
    <div class="col-md-4 col-sm-12" style="background-color: purple;">
      One of three columns
    </div>
  </div>
</div>
```

`col-md-4` means that on medium sized screens this div will span 4 columns. `col-sm-12` means that on a small sized screen this div will span 12 columns.

Here's the full table of screen sizes taken from their website (link on top of this script):

![Table of sizes](https://i.imgur.com/Vdyxdsj.png)

# Bootstrap Components

Bootstrap's other strength is in its components. There's a lot of pre-built pre-styled components we can use by copying and pasting blocks of code from their official documentation. Here's an example component of a [Card](https://getbootstrap.com/docs/4.5/components/card/#titles-text-and-links):

```html
<div class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of
      the card's content.
    </p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
```

With minor edits to make it display my info:

```html
<div class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">TheMshary</h5>
    <h6 class="card-subtitle mb-2 text-muted">30 repositories</h6>
    <p class="card-text">
      I make repositories about random stuff, educational stuff, and more random
      stuff spurred on by inspiration.
    </p>
    <a href="#" class="card-link">Github</a>
    <a href="#" class="card-link">Top Repo</a>
  </div>
</div>
```

There's many many more components in Bootstrap you can use.

---

## Task

(Set the time limit.)

Use Bootstrap to layout your portfolio and to style your webpage.

1. Make sure to use the Grid System.
2. Use some Bootstrap components.

Enjoy!
