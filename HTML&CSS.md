# CSS Box Model

## Parts of the Box Model

The CSS Box Model has 4 main parts:

1. Content
2. Padding
3. Border
4. Margin

---

## 1. Content

The content is the actual text, image, or other data inside the element.

Example:

```html
<div class="box">Hello World</div>
```

```css
.box {
  width: 200px;
  height: 100px;
  background-color: lightblue;
}
```

Here:

* Width = 200px
* Height = 100px
  This is the **content area**.

---

## 2. Padding

Padding is the space between the content and the border. It creates space inside the box.

Example:

```css
.box {
  padding: 20px;
}
```

Now:

* 20px space is added inside the box on all sides.

You can also control each side separately:

```css
padding: 10px 20px 30px 40px;
/* top right bottom left */
```

---

## 3. Border

Border goes around the padding and content.

Example:

```css
.box {
  border: 5px solid black;
}
```

Here:

* Border thickness = 5px
* Style = solid
* Color = black


---

## 4. Margin

Margin is the space outside the border.

Example:

```css
.box {
  margin: 30px;
}
```

Now:

* 30px space is added outside the box.

Like padding, margin can also be controlled individually:

```css
margin: 10px 20px 30px 40px;
/* top right bottom left */
```

---

## How Total Width and Height Are Calculated

By default, the total size of the element is:

Total Width =
content width + left padding + right padding + left border + right border

Example:

```
width: 200px
padding: 20px
border: 5px
```

Total width =
200 + 20 + 20 + 5 + 5 = 250px

---

Here is your **README.md** file content for:

**Inline vs Block Elements**

You can copy and paste this into your `README.md`.

---
---

# Inline vs Block Elements in HTML

# 1. Block Elements

A block element:

* Takes full width of the page and always starts on a new line
* Can contain other block and inline elements

## Common Block Elements

* `<div>`
* `<p>`
* `<h1>` to `<h6>`

## Example

```html
<h1>This is a heading</h1>
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

* Here each `<p>` appears on a new line.

## Styling Example

```css
div {
  width: 300px;
}
```

Even if you set width to 300px, it still starts on a new line.

---

# 2. Inline Elements

An inline element:

* Does NOT start on a new line
* Only takes as much width as needed

## Common Inline Elements

* `<span>`
* `<a>`
* `<strong>`

## Example

```html
<p>This is a <span>simple</span> example.</p>
```

Here:

* `<span>` stays inside the paragraph.
* It does not move to a new line.

Another example:

```html
<a href="#">Link 1</a>
<a href="#">Link 2</a>
```

All links appear on the same line .

---

# Changing Display Type

You can change the behavior using CSS `display` property.

## Make Inline Element Act Like Block

```css
span {
  display: block;
}
```

## Make Block Element Act Like Inline

```css
div {
  display: inline;
}
```

---

# Inline-Block

There is another value:

```
display: inline-block;
```

* Does NOT start on new line
* Allows setting width and height

---
---

# CSS Positioning: Relative and Absolute

# 1. position: relative

* You can move it using `top`, `right`, `bottom`, and `left`.
* The original space of the element is still reserved.

## Example

```html
<div class="box">Relative Box</div>
```

```css
.box {
  position: relative;
  top: 20px;
  left: 30px;
}
```
* The box moves 20px down.
* The box moves 30px right.
* But its original space is still kept.

---

# 2. position: absolute

* It does NOT keep its original space.
* It is positioned relative to its nearest positioned element (relative, absolute, fixed).

---

## Example Without Relative Parent

```html
<div class="box">Absolute Box</div>
```

```css
.box {
  position: absolute;
  top: 50px;
  left: 50px;
}
```
* The box is positioned from the top-left of the page.
---

# Absolute Inside Relative

## Example

```html
<div class="parent">
  <div class="child">Absolute Child</div>
</div>
```

```css
.parent {
  background-color: lightgray;
  position: relative;
}

.child {
  background-color: orange;
  position: absolute;
  top: 20px;
  right: 20px;
}
```

* The parent has `position: relative`.
* The child has `position: absolute`.
* The child moves relative to the parent.
* It stays inside the parent.

---
---

# Common CSS Structural Classes

Structural classes are CSS classes used to organize and structure a webpage layout. They help divide the page into sections like:

* Header
* Navigation
* Main content
* Sidebar
* Footer
* Row, Column

---

# 1. Header

The header is used for the top section of a website.

## Example

```html
<header class="header">
  <h1>My Website</h1>
</header>
```
---

# 2. Navigation

Navigation contains links to different pages.

## Example

```html
<div class="nav">
  <a href="#">Home</a>
  <a href="#">About</a>
</div>
```

---

# 3. Main Content

Main content is the primary section of the page.

## Example

```html
<div class="main">
  <h2>Main Content</h2>
  <p>This is the main area.</p>
</div>
```

---

# 4. Sidebar

A sidebar is used for extra information like:

* Links, Ads, Categories

## Example

```html
<div class="sidebar">
  <p>Sidebar content</p>
</div>
```
---

# 5. Footer

Footer is the bottom section of the webpage.

It usually contains:

* Copyright
* Contact info
* Social links

## Example

```html
<footer class="footer">
  <p>Copyright 2026</p>
</footer>
```
---

# 6. Row and Column

These are commonly used for grid layouts.

## Example Layout

```html
<div class="row">
  <div class="column">Column 1</div>
</div>
```

```css
.row {
  display: flex;
}

.column {
  flex: 1;
  padding: 10px;
  border: 1px solid black;
}
```

---
---

# Common CSS Styling Classes

Styling classes are used to change the appearance of elements.

They control:

* Colors, Text styles, Background, Spacing
* Borders, Shadows, Alignment

These classes help make websites look better and more organized.

---

# 1. Text Color Classes

Used to change text color.

## Example

```html
<p class="text-blue">This is blue text</p>
```

```css
.text-blue {
  color: blue;
}
```

---

# 2. Background Color Classes

Used to change background color.

## Example

```html
<div class="bg-dark">Dark Background</div>
```

```css
.bg-dark {
  background-color: black;
  color: white;
}
```

---

# 3. Text Alignment Classes

Used to align text.

## Example

```html
<p class="text-center">Center text</p>
<p class="text-right">Right text</p>
```

```css
.text-center {
  text-align: center;
}

.text-right {
  text-align: right;
}
```

---

# 4. Font Size Classes

Used to control text size.

## Example

```html
<p class="small-text">Small text</p>
<p class="large-text">Large text</p>
```

```css
.small-text {
  font-size: 12px;
}

.large-text {
  font-size: 24px;
}
```

---

# 5. Margin and Padding Classes

Used to control spacing.

## Example

```html
<div class="m-20 p-10">Box with spacing</div>
```

```css
.m-20 {
  margin: 20px;
}

.p-10 {
  padding: 10px;
}
```
---

# 6. Border Classes

Used to add borders.

## Example

```html
<div class="border-box">Bordered Box</div>
```

```css
.border-box {
  border: 2px solid black;
}
```

---

# 7. Shadow Classes

Used to add shadow effect.

## Example

```html
<div class="shadow-box">Shadow Example</div>
```

```css
.shadow-box {
  box-shadow: 2px 2px 10px gray;
}
```

---

# 8. Display Utility Classes

Used to change display behavior.

## Example

```html
<div class="d-block">Block Element</div>
```

```css
.d-block {
  display: inline-block;
}
```
---
---

# CSS Specificity

CSS Specificity decides which CSS rule is applied when multiple rules target the same element.

Specificity is like a priority system.

# Specificity Order (Low to High)

1. Element selector (p, div, h1)
2. Class selector (.class)
3. ID selector (#id)
4. Inline style
5. !important (highest priority)

---

# 1. Element Selector (Lowest)

Example:

```css
p {
  color: green;
}
```

This has the lowest priority.

---

# 2. Class Selector

Example:

```css
.text {
  color: blue;
}
```

Class selectors have higher priority than element selectors.

---

# 3. ID Selector

Example:

```css
#title {
  color: red;
}
```

ID selectors have higher priority than class selectors.

---

# 4. Inline Style

Inline styles are written inside HTML.

Example:

```html
<p style="color: purple;">Hello</p>
```

---

# 5. !important (Highest)

Example:

```css
p {
  color: green !important;
}
```

`!important` overrides almost everything.

---

# Specificity Value System

Specificity can be calculated as numbers.

Format:

Inline style → 1000
ID → 100
Class → 10
Element → 1

# Multiple Selectors Example

```css
div p {
  color: blue;
}
```

Specificity:

* div = 1
* p = 1

Total = 2

Example:

```css
.container p {
  color: red;
}
```

Specificity:

* .container = 10
* p = 1

Total = 11

The second rule wins.

---
---

# CSS Responsive Queries (Media Queries)

Responsive design means making a website look good on:

* Desktop
* Tablet
* Mobile

CSS Media Queries help us change styles based on screen size.

A media query is a CSS rule that applies styles only when certain conditions are true.


```css
@media (condition) {
  /* CSS rules here */
}
```
---

# Basic Example

```css
body {
  background-color: lightblue;
}
@media (max-width: 600px) {
  body {
    background-color: lightgreen;
  }
}
```

Explanation:

* If screen width is 600px or less
* Background becomes lightgreen
* Otherwise, it stays lightblue

---

# Common Breakpoints

These are commonly used screen sizes:

* Mobile: max-width: 480px
* Tablet: max-width: 1024px
* Desktop: 1025px and above

---

# min-width vs max-width

## max-width

Applies styles up to a certain width.

```css
@media (max-width: 600px) {
  /* Mobile styles */
}
```

Used in mobile-first approach.

---

## min-width

Applies styles from a certain width and above.

```css
@media (min-width: 768px) {
  /* Tablet and desktop styles */
}
```
---
---

# CSS Flexbox and CSS Grid


## CSS Flexbox

Flexbox is used to arrange items in:

* A row
* Or a column

It makes alignment and spacing very easy.

---

## Step 1: Make a Flex Container

```css
.container {
  display: flex;
}
```

All direct children become flex items.

---

## Example

### HTML

```html
<div class="container">
  <div class="box">1</div>
  <div class="box">2</div>
  <div class="box">3</div>
</div>
```

### CSS

```css
.container {
  display: flex;
}

.box {
  padding: 20px;
  border: 1px solid black;
}
```

Result:
Boxes appear side by side.

---

## Important Flexbox Properties

### 1. flex-direction

Controls direction of items.

```css
flex-direction: row; 
```

---

### 2. justify-content

Aligns items horizontally (main axis).

```css
justify-content: center;
```

---

### 3. align-items

Aligns items vertically (cross axis).

```css
align-items: center;
```

---

### 4. flex

Controls item size.

```css
.box {
  flex: 1;
}
```

All boxes take equal width.

---
# CSS Grid

Grid is used to create layouts with:

* Multiple rows
* Multiple columns

It is powerful for full page layouts.

---

## Important Grid Properties

### 1. grid-template-columns

Defines number and size of columns.

```css
grid-template-columns: 200px 200px;
```

---

### 2. grid-template-rows

Defines row sizes.

```css
grid-template-rows: 100px 200px;
```

---

### 3. gap

Space between rows and columns.

```css
gap: 20px;
```

---

### 4. grid-column and grid-row

Used to make items span multiple columns.

```css
.box1 {
  grid-column: span 2;
}
```