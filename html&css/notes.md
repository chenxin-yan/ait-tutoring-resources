# HTML & CSS

## HTML

HTML is markup language that describes the structure/content of a web page. We call each "thing" described using HTML an "element"

```html
<!doctype html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>My First Heading</h1>
    <p>My first paragraph.</p>
  </body>
</html>
```

### HTML tags

To "markup" the content of a web page, we need to something called "HTML Tags". There are two types of tags:

- opening/closing tags
- self-closing tags

You can learn more about all the tags that are available [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Cheatsheet). We are only going to cover the most basic and common ones.

#### Opening/closing tags

```html
opening tag closing tag v v
<p>I am a paragraph</p>
```

- `<div></div>` (more on this later)
- paragraph: `<p></p>`
- headers: `<h1></h1>` `<h2></h2>` ...
- unordered list:

```html
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

- ordered list:

```html
<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

- bold: `<b></b>` and `<strong></strong>` (more on this later)
- italic: `<i></i>` and `<em></em>` (more on this later)
- anchor(link): `<a></a>`
- and more...

#### Self-closing Tags

- newline: `<br>`
- image: `<img>`
- and more...

### HTML attributes

- All HTML elements can have *attributes*
- Attributes provide **additional information** about elements
- Attributes are always specified in **the opening tag**
- Attributes usually come in name/value pairs: `name="value"`

```html
<a href="https://www.mywebsite.com">link</a>
```

### Semantic HTML

#### Semantic elements

You might notice that `<div>` tag doesn't deliver any semantic meanings. It is used to group elements without introducing anything semantic meanings.

What if I want to group some elements with semantic meanings such as I want to represent "elements inside of this tag is navbar" or "elements inside of this tag in the article"?

This is when the semantic elements come in. You can find some examples [here](https://www.w3schools.com/html/html5_semantic_elements.asp).

**Why do we care? If these semantic elements look the same as `div`, why should we use them?** Well... here are some benefits:

- for accessibility reason
  - screen readers etc.
- for browser to better understand the page so some browsers provides special optimization/features for the page
  - reader mode and so on

#### `<b>` Vs. `<strong>` Elements

- `<b>` defines a bold text
- `<strong>` defines an important text, which is bold visually.

```html
<b>This text is bold</b> <strong>This text is important!</strong>
```

#### `<i>` And `<em>` Elements

- `<i>` defines italic text
- `<em>` defines emphasized text, which is italicized visually.

```html
<i>This text is italic</i> <em>This text is emphasized</em>
```

## CSS

Imagine we now have the elements that we want to have laid out on the page, how should I make it so it looks exactly what we want? We could use **CSS**

### Use css in html document

#### External CSS

Reference the css file under `<head>`, and write css in that file

```html
<!doctype html>
<html>
  <head>
    <link href="style.css" rel="stylesheet" />
  </head>
  <body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

#### Internal CSS

write css code under `<style>` in `<head>`. Internal CSS is **not recommended** but it can be used in simple project

```html
<!doctype html>
<html>
  <head>
    <style>
      body {  background-color: linen;}

      h1 {  color: maroon;
        margin-left: 40px;}
    </style>
  </head>
  <body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

#### Inline CSS

add styling directly to the HTML elements. Inline CSS is **not recommended** and should be avoided for maintenance purposes. However, there is something called [tailwindCSS](https://tailwindcss.com) that gives inline CSS a good DX by providing utility classes.

```html
<!doctype html>
<html>
  <body>
    <h1 style="color:blue;text-align:center;">This is a heading</h1>
    <p style="color:red;">This is a paragraph.</p>
  </body>
</html>
```

### Selectors

Given that we are using CSS to style the elements, we would need to specify which element that certain style rules apply to. Learn more about selectors [here](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors)

#### Element Selector

```css
p { 
  text-align: center;
  color: red;
}
```

#### ID Selector

We can give an id to an element through html attribute and select that element using CSS selectors. Generally, we want to make sure id is unique across the page.

```css
#para1  {
  text-align: center;
    color: red;
}
```

#### Class Selector

We can give an class to an element through html attribute and select that element using CSS selectors. Generally, class names can be used by multiple elements

```css
.center  {
  text-align: center;
  color: red;
}
```

#### Grouping Selectors

```css
h1,
h2,
p  {
  text-align: center;
    color: red;
}
```

#### Universal Selector

```CSS
* {
  text-align: center;
  color: blue;
}

```

### Box Models

The box model refers to different parts of every HTML element.

- **Content**
- **Padding**
- **Border**
- **Margin**

```
 -----------------------------
|           Margin            |
|   -----------------------   |
|  |        Border         |  |
|  |   -----------------   |  |
|  |  |     Padding     |  |  |
|  |  |  -------------  |  |  |
|  |  |  |  Content  |  |  |  |
|  |  |  -------------  |  |  |
|  |   -----------------   |  |
|   -----------------------   |
 -----------------------------
```

There are different types of boxes such as block-level, inline-level, and inline-block boxes.

- Learn more about box modals [here](https://www.w3schools.com/css/css_boxmodel.asp).
- Learn more about how to calculate the size of the element and `border-box` [here](https://www.w3schools.com/css/css3_box-sizing.asp).

### What are some styles/properties we can apply using CSS?

**There is a lot!!**

I would suggest looking up options as needed when you are working with CSS so it would be less overwhelming at first. You can find reference [there](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference).

For example, if I want to change the font size somehow, I would search "font". I would be able to see an option called `font-size` which takes in the size as value. Great!

## And more

### some vscode plugins

- Auto Rename Tag: help you rename the other tag as you change either the opening/closing tag
- Color Info: show inline css color info

### some neovim plugins

- you can find my config [here](https://github.com/chenxin-yan/nix-dotfiles/blob/main/config/nvim/lua/cyan/plugins/languages/web.lua)
