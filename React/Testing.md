# Testing with React

## Jest and Native

in package.json you need to override every image import

```json
"jest": {
    "preset": "jest-expo",
    "moduleNameMapper": {
      "\\.(jpg|jpeg|png|svg)$": "<rootDir>/__mocks__/imageMock.js"
    }
  },
```

add a `./__mocks__/imageMocks`

```js
// mock file to override every image import

module.exports = 'mock-image';
```
