# Typescript with React

Using **interfaces** to describe both the **shape of props and state** for every component is going to make development much more enjoyable. 😎

When writing JSX, just trigger **autocompletion** (ctrl + space on Windows) inside a component tag to see the available props it can accept. 🤯

```js

interface Address {
  street: string;
  city: string;
  number: number;
  zip: number;
}

interface PersonProps {
  name: string;
  age: number;
  address?: Address;
  phoneNumber?: string;
}

const Person = (props: PersonProps) => {
  ...
}

const List = () => {
  // toggle autocompletion on the * mark
  return <div>
    <Person  * />
    <Person/>
    <Person/>
    <Person/>
    <Person/>
  </div>
}
```

## Start new project

`npx create-react-app my-app --template typescript`
