# Animations in CSS

# Fix glitchy animations

Elements go back to their default style after an animation is complete. To avoid this behaviour and make it so they stay in their final state add this property

```css
.moving {
  animation-fill-mode: both;
}
```

## Loading spinners

![result](https://media.giphy.com/media/2Jfe3aQ9I9reo0163Y/giphy.gif)

[codepen](https://codepen.io/vikvikvr/pen/vYxeNjr)

### Extra resources and tools 🔗

- [Gsap](https://greensock.com/gsap/)
