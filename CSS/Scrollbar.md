# Styling scrollbars

The **default scrollbar** is kinda ugly (at least on windows). We can customize it with the `::-wekbit-scrollbar` family of selectors.

## Horizontal scrollbar

For instance with a scrolling **gallery of pictures**.

```scss
.container {
  overflow-x: scroll;
  &::-webkit-scrollbar {
    height: 10px;
  }

  &::-webkit-scrollbar-thumb {
    border-radius: 20px;
    background-color: orange;
  }
}
```
