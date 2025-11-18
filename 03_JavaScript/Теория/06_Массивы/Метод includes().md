Метод includes() позволяет нам узнать если заданое значение в масиве

```js
const friends = ['Mango', 'Kiwi', 'Poly', 34, 'Ajax'];

const isPolyFriend = friends.includes('Poly')
const isNumberFriend = friends.includes(34)

console.log(isPolyFriend); // true
console.log(isNumberFriend); // true
```

! Работает только с простыми типами данных в масиве

```js
const friends = ['Mango', 'Kiwi', 'Poly', 'Ajax', ['Neptun', 'Saturn']];

const isPolyFriend = friends.includes(['Neptun', 'Saturn'])

console.log(isPolyFriend); // false
```
