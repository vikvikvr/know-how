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

Cool explanation [here](https://blog.bitsrc.io/how-to-use-sass-and-css-modules-with-create-react-app-83fa8b805e5e).

## Adding GSAP animations

[Guide](https://greensock.com/react/)

We can now use hooks!

## Animate route changes

http://reactcommunity.org/react-transition-group/with-react-router/

## Components from svg files

You can turn any .svg file to a React component very easily

```jsx
import React from 'react';
import { ReactComponent as Logo } from './logo.svg';

const Icon = () => {
  return (
    <div className="icon-container">
      <Logo />
    </div>
  );
};

// ⚠ Only works with create-react-app
```

**Styling** its container will affect also the graphic itself

```css
.icon-container {
  width: 100px;
  height: 100px;
  fill: white;
}
```

## Conditional classes

When adding **multiple classes** to an element **conditionally**, we need to use if statements or ternary operators. It might get out of hand really quick, also having to keep track of the needed **white space** prefixes.

```js
// 1. boring 😴

let btnClasses = 'btn';

if (isPressed) btnClasses += ' btn-pressed';
else if (isHovered) btnClasses += ' btn-over';

return <button className={btnClasses}>click me</button>;
```

Using the package [classnames](https://www.npmjs.com/package/classnames), the code becomes much more readable and maintainable.

```js
// 2. like a boss 🤙

import classNames from 'classnames';

const btnClasses = classNames({
  btn: true,
  'btn-pressed': isPressed,
  'btn-over': !isPressed && isHovered
});

return <button className={btnClass}>click me</button>;
```
