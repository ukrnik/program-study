## Task 1

```js
function slugify(title){
const titleTrim = title.trim().toLowerCase();
const word = titleTrim.split(" ");
return word.join("-");
}

console.log(slugify("Arrays for begginers ")); // "arrays-for-begginers"

console.log(slugify("English for developer ")); // "english-for-developer"

console.log(slugify(" Ten secrets of JavaScript")); // "ten-secrets-of-javascript"

console.log(slugify("How to become a JUNIOR developer in TWO WEEKS")); // "how-to-become-a-junior-developer-in-two-weeks"
```
## Task 2

```js
function makeArray(firstArray, secondArray, maxLength) {
const arrayCompact = firstArray.concat(secondArray);
const arrayLenght = arrayCompact.slice(0, maxLength);
return arrayLenght
}

console.log(makeArray(["Mango", "Poly"], ["Ajax", "Chelsea"], 3)); // ["Mango", "Poly", "Ajax"]

console.log(makeArray(["Mango", "Poly", "Houston"], ["Ajax", "Chelsea"], 4)); // ["Mango", "Poly", "Houston", "Ajax"]

console.log(makeArray(["Mango"], ["Ajax", "Chelsea", "Poly", "Houston"], 3)); // ["Mango", "Ajax", "Chelsea"]

console.log(makeArray(["Earth", "Jupiter"], ["Neptune", "Uranus"], 2)); // ["Earth", "Jupiter"]

console.log(makeArray(["Earth", "Jupiter"], ["Neptune", "Uranus"], 4)); // ["Earth", "Jupiter", "Neptune", "Uranus"]

console.log(makeArray(["Earth", "Jupiter"], ["Neptune", "Uranus", "Venus"], 0)); // []
```
## Task 3

```js
function filterArray(numbers, value) {
let arrayResult = [];
for (const rightNumber of numbers) {
if (rightNumber > value) {
arrayResult.push(rightNumber);
        }
    }
return arrayResult;
}

console.log(filterArray([1, 2, 3, 4, 5], 3)); // [4, 5]

console.log(filterArray([1, 2, 3, 4, 5], 4)); // [5]

console.log(filterArray([1, 2, 3, 4, 5], 5)); // []

console.log(filterArray([12, 24, 8, 41, 76], 38)); // [41, 76]

console.log(filterArray([12, 24, 8, 41, 76], 20)); // [24, 41, 76]
```