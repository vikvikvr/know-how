# React Know-how

1. [Props](https://github.com/vikvikvr/know-how/blob/master/React/Props.md)
2. [State](https://github.com/vikvikvr/know-how/blob/master/React/State.md)
3. [Clicks](https://github.com/vikvikvr/know-how/blob/master/React/Clicks.md)
4. [Forms](https://github.com/vikvikvr/know-how/blob/master/React/Forms.md)
5. [Async](https://github.com/vikvikvr/know-how/blob/master/React/Async.md)
6. [Lifecycle hooks](https://github.com/vikvikvr/know-how/blob/master/React/Lifecycle.md)
7. [Typescript](https://github.com/vikvikvr/know-how/blob/master/React/Typescript.md)

## Using Sass stylesheets

`npm i node-sass`

## Using FontAwesome icons

Install required **dependencies** ⏬

`npm i @fortawesome/fontawesome-svg-core @fortawesome/free-solid-svg-icons @fortawesome/react-fontawesome`

Use an **icon** in your component

```ts
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faSearch } from '@fortawesome/free-solid-svg-icons';

const Component = (props) => {
  return <FontAwesomeIcon icon={faSearch} size="1x" color="white" />;
};
```

Read the **docs** [here](https://fontawesome.com/v5.15/how-to-use/on-the-web/using-with/react). 👈

## CSS modules

Turning a stylesheet into a module makes it scoped to the component itself. Using the same class names won't collide with other stylesheets because React will prefix them with the name of the component.

Inside the component itself, we can now access the class names

```js
import styles from './Button.module.scss';

const Button = (props) => {
  return <button className={styles.btn}>click me</button>;
};
```

This helps making sure you use the correct class names, and get notified when they change.

Cool explanation [here](https://blog.bitsrc.io/how-to-use-sass-and-css-modules-with-create-react-app-83fa8b805e5e)
