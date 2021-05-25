# Typography

As a good practice, you would want to **set** `font-size` **only once** at the top level, and then refer to it using the `em` unit.

This allows us to change mind later very easily, without having to go through all your styles to make changes.

```css
body {
  font-size: 18px;
}
.hero-title {
  /* effectively 4 times 18px */
  font-size: 4em;
}
.feature-title {
  font-size: 1.5em;
}
```

## Fix packed text

When dealing with **long paragraphs**, the lines might come as too close to each others. Adding some space between them will make those text-walls more plasing to the eye.

```css
.feature-description {
  font-size: 1.5em;
  /* effectively adds a 0.5em padding between lines */
  line-height: 2em;
}
```
