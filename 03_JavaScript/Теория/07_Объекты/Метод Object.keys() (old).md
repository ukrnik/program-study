приймає об'єкт і повертає масив ключів його властивостей. Якщо в об'єкті немає властивостей, метод поверне порожній масив.

```js
const book = {
  title: "The Last Kingdom",
  author: "Bernard Cornwell",
  genres: ["historical prose", "adventure"],
  rating: 8.38,
};
const keys = Object.keys(book);
console.log(keys); // ['title', 'author', 'genres', 'rating']
```

Скомбінувавши результат `Object.keys()` і [[Цикл for...of]], можна зручно перебрати властивості об'єкта, не вдаючись до використання циклу [[Цикл for...in]].

```js
const book = {
  author: "Bernard Cornwell",
  genres: ["historical prose", "adventure"],
  rating: 8.38,
};
const keys = Object.keys(book);

for (const key of keys)
  console.log(key); // Ключ
  console.log(book[key]); // Значення властивості
}
```

Ми перебираємо масив ключів об'єкта і на кожній ітерації отримуємо ключ і значення властивості.
## Синтаксис

Object.keys(obj)
### Параметры

`obj`

Объект, чьи собственные перечисляемые свойства будут возвращены.
## Описание

Метод `Object.keys` возвращает массив строковых элементов, соответствующих именам перечисляемых свойств, найденных непосредственно в самом объекте. Порядок свойств такой же, как и при ручном перечислении свойств в объекте через цикл.
## Примеры

```js
const arr = ["a", "b", "c"];
console.log(Object.keys(arr)); // консоль: ['0', '1', '2']

// Массивоподобный объект
const obj = { 0: "a", 1: "b", 2: "c" };
console.log(Object.keys(obj)); // консоль: ['0', '1', '2']

// Массивоподобный объект со случайным порядком ключей
const an_obj = { 100: "a", 2: "b", 7: "c" };
console.log(Object.keys(an_obj)); // консоль: ['2', '7', '100']
```
