`Object.values(object)` повертає **масив значень його властивостей**.

  Якщо в об'єкті відсутні властивості, метод `Object.values(object)` поверне порожній масив.

```js
const book = {
  title: "The Last Kingdom",
  author: "Bernard Cornwell",
  rating: 8.38,
};
const keys = Object.keys(book);
console.log(keys); // ["title", "author", "rating"]

const values = Object.values(book);
console.log(values); // ["The Last Kingdom", "Bernard Cornwell", 8.38]
```

Масив значень властивостей також можна перебрати циклом [[Цикл for...of]], наприклад для отримання загальної суми числових значень.
## Синтаксис

Object.values(obj)

## Параметры

`obj`

Объект, чьи значения перечисляемых свойств будут возвращены.

## Возвращаемое значение

Массив содержащий значения перечисляемых свойств объекта.

## Описание

`Object.values()` возвращает массив, чьи элементы это значения перечисляемых свойств найденных в объекте. Порядок такой же как если пройтись по объекту циклом вручную.

## Примеры

```js
const obj = { foo: "bar", baz: 42 };
console.log(Object.values(obj)); // ['bar', 42]

// Массив как объект
const obj = { 0: "a", 1: "b", 2: "c" };
console.log(Object.values(obj)); // ['a', 'b', 'c']

// Массив как объект со случайным порядком ключей
// Когда мы используем нумерованные ключ, значения возвращаются в порядке возрастания
const an_obj = { 100: "a", 2: "b", 7: "c" };
console.log(Object.values(an_obj)); // ['b', 'c', 'a']
```