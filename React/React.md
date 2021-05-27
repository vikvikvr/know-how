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
