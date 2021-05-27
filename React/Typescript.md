# Typescript with React

You can opt-in for Typescript when creating a project

`npx create-react-app my-app --template typescript`

Using **interfaces** to describe both the **shape of props and state** for every component is going to make development much more enjoyable. 😎

When writing JSX, just trigger **autocompletion** (ctrl + space on Windows) inside a component tag to see the available props it can accept. 🤯

```js
interface Props {
  name: string;
  age: number;
  phoneNumber?: number;
}

const Person = (props: Props) => {
  ...
}

const List = () => {
  // toggle autocompletion on the * mark
  return <div>
    <Person  * />
    <Person/>
    <Person/>
  </div>
}
```
