# Layouts

When working with layouts it's very helpful to **see the borders** of everything

```css
div,
nav,
section {
  border: 1px solid red;
}
```

Different selectors can be added as needed (h1, p, span, a, ul, li).

## Page layout

The body for a **landing page** is pretty standard: it contains a top navigation and a footer with stacked sections in between.

```html
<body>
  <nav>navigation bar</nav>
  <section>hero + call to action</section>
  <section>features</section>
  <section>testimonials?</section>
  <section>call to action2</section>
  <section>newsletter?</section>
  <section>call to action3</section>
  <footer>more links</footer>
</body>
```

The page has usually **2 big paddings on each side**, so the content looks kinda centered and there is some white space to work with:

```css
nav {
  padding: 0 150px;
}
body {
  padding: 0 150px;
}
footer {
  padding: 0 150px;
}
```

Notice how the actual elements still have their borders at the edges of the screen, we just push their content inwards.

## Navbar layout

Again, pretty standard: we usually want a logo placed on the left side, followed by two groups (text/links) with space between them.

`|--LOGO---link1-link2--------------link4-link5-link6--|`

```html
<nav>
  <div>
    <img class="nav-logo-image" />
    <ul class="nav-links-left"></ul>
  </div>
  <ul class="nav-links-left"></ul>
</nav>
```

```scss
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  .nav-links-left {
    // to push first links away from logo
    margin-left: 2em;
  }
  div {
    // to push second links to the far right
    margin-right: auto;
  }
}
```

We use .SCSS to leverage **rules nesting**.

## Hero layout

This can vary a lot, sometimes it's 1 centered content, other times is a 2-columns layout.

## Features layout

It's usually a **multiple-columns** layout: each one has an optional icon/image, a title and a brief description.

`--ICON1-----ICON2-----ICON3--`
`--TITLE-----TITLE-----TITLE--`
`--DESCR-----DESCR-----DESCR--`

```html
<div class="features-container">
  <div class="feature-column">
    <div class="feature-icon">ICON1</div>
    <h1 class="feature-title">TITLE</h1>
    <p class="feature-description">DESCR</p>
  </div>
  <div class="feature-column">
    <div class="feature-icon">ICON2</div>
    <h1 class="feature-title">TITLE</h1>
    <p class="feature-description">DESCR</p>
  </div>
  <div class="feature-column">
    <div class="feature-icon">ICON3</div>
    <h1 class="feature-title">TITLE</h1>
    <p class="feature-description">DESCR</p>
  </div>
</div>
```

```css
.features-container {
  display: flex;
  justify-content: space-between;
  padding: 0 50px;
}

.feature-icon {
  width: 100px;
  height: 100px;
  border-radius: 200px;
  background: red;
}

.feature-column {
  max-width: 400px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
```
