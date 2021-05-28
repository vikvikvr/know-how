# CSS Secrets

## Clip image to path

![preview](https://media.giphy.com/media/Z5j4FJh3W6dzbS9z87/giphy.gif)

[codepen](https://codepen.io/vikvikvr/pen/xxqrQZr)

[custom shapes editor](https://bennettfeely.com/clippy/)

## Diagonal line

![result](https://media.giphy.com/media/JZhlAbmPIcxaggGOTK/giphy.gif)

[codepen](https://codepen.io/vikvikvr/pen/YzZxgMJ)

## Add commas after list items

given this html structure

```html
<ul>
  <li>Alpha</li>
  <li>Beta</li>
  <li>Gamma</li>
</ul>
```

You can add a comma to each item, except for the last

```css
ul {
  display: flex;
}
ul > li:not(:last-child)::after {
  content: ', ';
}
```

The result will look like this

```
Alpha, Beta, Gamma
```

## To study more

https://dev.to/nimritee12/15-advanced-css-techniques-to-master-in-2021-1g9d
