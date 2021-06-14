# CSS Know-how

1. [Reset Styles](https://github.com/vikvikvr/know-how/blob/master/CSS/ResetStyles.md)
2. [Layouts](https://github.com/vikvikvr/know-how/blob/master/CSS/Layouts.md)
3. [Typography](https://github.com/vikvikvr/know-how/blob/master/CSS/Typography.md)
4. [Custom Fonts](https://github.com/vikvikvr/know-how/blob/master/CSS/Fonts.md)
5. [Scrollbar](https://github.com/vikvikvr/know-how/blob/master/CSS/Scrollbar.md)
6. [Sass](https://github.com/vikvikvr/know-how/blob/master/CSS/Sass.md)
7. [Animations](https://github.com/vikvikvr/know-how/blob/master/CSS/Animations.md)
8. [Secrets](https://github.com/vikvikvr/know-how/blob/master/CSS/Secrets.md)

## Things I will learn next

- Subgrids

## Mask image with gradient

Just apply the `mask-image` property to the image itself

```css
#masked {
  mask-image: linear-gradient(to top, transparent 5%, black 75%);
}
```

Anything **black** will be visible 🐵, anything **transparent** will be hidden 🙈 instead

![img](https://i.imgur.com/A7chZCu.png)

[codepen](https://codepen.io/vikvikvr/pen/MWpXaRV)

## Loaders collection

- by [dev.to/kiranrajvjd](https://dev.to/kiranrajvjd/35-simple-css-based-pre-loaders-gfl)
- by [https://dev.to/afif](https://dev.to/afif/i-made-100-more-css-loaders-for-your-next-project-4ioa)

## Scroll Snap

```html
<div class="parent">
  <div class="child">lorem</div>
  <div class="child">ipsum</div>
  <div class="child">dolor</div>
</div>
```

```css
.parent {
  scroll-snap-type: y mandatory;
  overflow-y: scroll;
}

.child {
  scroll-snap-align: start;
}
```
