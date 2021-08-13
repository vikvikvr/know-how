# Extra javascript Snippets

## Shuffle an array

Using a very nice sorting callback

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];

const shuffled = numbers.sort(() => Math.random() - 0.5);
```

## Swap 3 values

Using destructuring

```js
let a = 5;
let b = 8;

[a, b] = [b, a];
```

## Check palindrome

Turning the word into an array for easy reversing

```js
function checkPalindrome(word = '') {
  const reversed = word.split('').reverse().join('');

  return word === reversed;
}
```
