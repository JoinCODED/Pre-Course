## Introduction to CSS

CSS, short for Cascading StyleSheet, is a markup language for styling your webpage. Also every webpage on the internet that has any form of styles uses CSS to style. Styling means font formatting, colors, sizes, spacing between elements, and anything to do with presentation of the HTML content.

## Stylesheet

The stylesheet is a separate file with the `.css` extension that contains all our CSS code for the webpage.

So now remove the inline CSS code we just wrote, and move it to another file:

```css
h1 {
  color: red;
}
```

This is how you write CSS code in a stylesheet. You first enter the element you'd like to apply styles to, in this case `h1`, then in curly braces you'd enter the CSS properties and their values to be applied to this element. Here we have only one property, but you can have as many as you'd like.

This styling applies to _all_ `h1` elements on the page, not just one of them if you have multiple.

To link the new CSS file with our HTML file, you have to add a tag in the `<head>` element that links the two files:

```html
<link href="styles.css" rel="stylesheet" type="text/css" />
```

There's no need to get into how this tag works and what each attribute means. The only thing that matters is that this tag will link the CSS file with this HTML file, otherwise the CSS code you write won't take effect on your webpage. The `href` attribute contains the name and location of the CSS file.

Now the page should still be looking the same as it did before we moved our CSS to a stylesheet, if your code matches ours.

## `id`

What if you'd like to apply the same styles to different elements on the page? Well, here's where `id`s come in. Let's give one of our books an `id` so we can give it a background color:

```html
<li id="untethered-soul">"The Untethered Soul" by Michael Singer</li>
```

The `id` can be whatever you want it to be. Better make it something meaningful and easy to understand. Let's write CSS to change this book's background color!

```css
#untethered-soul {
  color: cyan;
  background-color: black;
}
```

The `#` here is necessary as it indicates that what comes next is an HTML `id`.

## `class`

What if you'd like to apply a styling to multiple elements that don't have the same name? Well, you can create a _`class`_ and apply that `class` to all those elements who share the same styling. Let's make the names of the artists behind the books and the songs _italic_. To do that, we'll wrap the names of the artists in a `<span>` element, and apply the class "`artists`" to the `<span>`s:

```html
<h2>
  Songs
</h2>
<ul>
  <li>"Fly Me To The Moon" by <span class="artists">Frank Sinatra</span></li>
  <li>"As Time Goes By" by <span class="artists">Seth MacFarlane</span></li>
  <li>"Helium" by <span class="artists">Sia</span></li>
</ul>

<h2>Books</h2>
<ol type="i">
  <li>
    "A Knight Of The Seven Kingdoms" by
    <span class="artists">George R. R. Martin</span>
  </li>
  <li id="untethered-soul">
    "The Untethered Soul" by <span class="artists">Michael A. S</span>inger
  </li>
  <li>"How To Fight A Hydra" by <span class="artists">Josh Kaufman</span></li>
</ol>
```

Then we can write the CSS to make them italic:

```css
.artists {
  font-style: italic;
}
```

## Multiple Tags

You can also apply the same styling to multiple tags at the same time! Let's center all `p` and `h1` elements on our page! You can do that by entering multiple elements in CSS, separated by commas:

```css
h1,
p {
  text-align: center;
}
```

---

## Task (Cont.)

(Set the time limit.)

Continuing the task...

1. Create a file in your `Portfolio` called `styles.css`.
2. Link your `styles.css` with your `index.html`.

   ```html
   <link href="styles.css" rel="stylesheet" type="text/css" />
   ```

3. Using CSS, style your webpage to your liking.

---

## Box Model

### Border

In CSS, you can add a _border_ to your elements. Let's see how we can put a border around our songs heading...

Let's give the heading an `id`:

```html
<h2 id="songs-heading">
  Songs
</h2>
```

Then in our CSS, let's add that border!

```css
#songs-heading {
  border: 1px solid black;
}
```

### Padding

I find it uncomfortable that the heading text is so close to the border. Let's add some spacing there!

```css
#songs-heading {
  border: 1px solid black;
  padding: 5px;
}
```

We just added some padding. The spacing between the content and the border around it is called _padding_.

If you noticed, the padding we added was applied not just to the left border, but also on all four sides. How can we specify that we want to set the padding only on the left? Here's how:

```css
#songs-heading {
  border: 1px solid black;
  padding-left: 5px;
}
```

`padding-left` is a property that applies padding only on the left side. There's also `padding-right`, `padding-top`, and `padding-bottom`. There's another way also to set different paddings to different sides:

```css
#songs-heading {
  border: 1px solid black;
  padding: 5px 0px 15px 10px;
}
```

This way of defining the padding property allows us to set different paddings for each side in one line. The first value, `5px` sets the top padding. Second value, `0px` sets the right padding. Third `15px` sets the bottom padding, and the fourth sets the left padding.

### Margin

You can also create spacing _between elements_ on the page. This is called a _margin_. Let's push our songs list inside he page a little bit, away from the left edge of the screen. We can do his by setting a left margin. Everything we mentioned before about padding applies to margins.

```html
<ul id="songs">
  <li>"Fly Me To The Moon" by Frank Sinatra</li>
  <li>"As Time Goes By" by Seth MacFarlane</li>
  <li>"Helium" by Sia</li>
</ul>
```

```css
#songs {
  margin-left: 15px;
  border-radius: 15px;
}
```

There! Looks better :D

### Box Model

These four elements: Border, Padding, Margin, and the element content itself are what the **Box Model** is. They create like a box around every HTML element.

---

## Colors

Colors are nice, aren't they? Don't you like it when you walk into a room and just see beautiful bright lovely colors that open up your heart for a hopeful tomorrow? Let's learn some more about colors in CSS! You can bring that feeling of joy to life on your website!!!

### Hex

You can represent colors in CSS using the hexidecimal number of a color, with a `#` before it. When you find a color shade you like online, you'll usually be given that color's hexidecimal code, which looks like this: `#ff0000`. This color is _Red_. Green is `#00ff00`. Blue is `#0000ff`. Cyan is `#00ffff`. A more complex example is the color Tomato: `#ff6347`.

So in CSS when you specify the color of something, like the heading, instead of typing the name of the color you want, you can enter the hex code for the exact shade you like:

```css
h1 {
  color: #ff6347;
  font-family: monospace;
}
```

### `rgb()`

`rgb` stands for Red, Green, and Blue. Every hex color can be represented differently in CSS using `rgb()`. Let's change the Tomato color from before to using `rgb()` instead of a hex code:

```css
h1 {
  color: rgb(255, 99, 71);
  font-family: monospace;
}
```

Each color consists of a combination of Red, Green, and Blue. So with `rgb()` you give it three numbers: First is how much Red, second is how much Green, third is how much Blue. The combination of those colors will create the resulting color you want, which in this case is Tomato shade of Red.

### `rgba()`

You can expand on this further by specifying _opacity_. From a range of 0-1, how _opaque_ is the content you're applying this color to? Opacity is the opposite of transparency. So if something is completely opaque, it's not transparent at all, and vice versa.

So to make our heading appear half transparent, we can use the following CSS code:

```css
h1 {
  color: rgba(255, 99, 71, 0.5);
  font-family: monospace;
}
```

The `a` in `rgba()` stands of _alpha_. The fourth number in `rgba()` is _opacity_. So `0.5` alpha is half transparent. If you make it `0` it'll be completely transparent and you won't see the content. The default value for opacity is `1`, which means it's completely opaque.
