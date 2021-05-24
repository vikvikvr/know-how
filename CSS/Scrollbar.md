horizontal scrollbar

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
