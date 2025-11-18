.split() создаёт масив из строки

```js
const title = 'JavaScript is awesome';

const arrayFromTitle = title.split(' ');

console.log(arrayFromTitle); // ['JavaScript', 'is', 'awesome']

----------------------------------------------------------------------------

const title = 'JavaScript is awesome';

const arrayFromTitle = title.split(); // если ничего не передать то вся строка запишется в масив

console.log(arrayFromTitle); // ['JavaScript is awesome']

----------------------------------------------------------------------------

const title = 'JavaScript is awesome';

const arrayFromTitle = title.split(""); // если мы передадим только кавички то метод разобьёт строку по буквам

console.log(arrayFromTitle); // ['J', 'a', 'v', 'a', 'S', 'c', 'r', 'i', 'p', 't', ' ', 'i', 's', ' ', 'a', 'w', 'e', 's', 'o', 'm', 'e']
```
