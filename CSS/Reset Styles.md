# Reset styles

When starting to work with CSS, it's helpful to "reset" default styles coming from a "hidden" stylesheet loaded by the browser itself.

### "Homemade" strategy

Just apply these styles at the top level of your app, to make sure selectors can work on any children.

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

This is a very rough an minimalistic approach, should be avoided in production.

### Better approach

Download a ready-to-use reset stylesheet, there are tons out there:

- [normalize.css](https://necolas.github.io/normalize.css/8.0.1/normalize.css)
- [html5 doctor](http://html5doctor.com/html-5-reset-stylesheet/)

Don't forget to include the link:css tag in your template.
