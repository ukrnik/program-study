## Описание

reduce() — это метод массива в JavaScript, который позволяет свести массив к одному значению, применяя функцию-аккумулятор к каждому элементу массива.

---
## Синтаксис

```js
array.reduce(callback[, initialValue])
```

- **callback** — функция, которая выполняется для каждого элемента массива и принимает четыре аргумента:
    - **accumulator** — накопленное значение (оно обновляется при каждом вызове callback).
    - **currentValue** — текущий элемент массива.
    - **index (необязательно)** — индекс текущего элемента.
    - **array (необязательно)** — исходный массив.

- **initialValue (необязательно)** — начальное значение для accumulator. Если не задано, reduce() использует первый элемент массива как начальное значение и начинает со второго элемента.
---
## Пример №1

```js
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(sum); // 15
```

- initialValue задан как 0
- На каждой итерации accumulator обновляется:
    - 1-я итерация: 0 + 1 = 1
    - 2-я итерация: 1 + 2 = 3
    - 3-я итерация: 3 + 3 = 6
    - 4-я итерация: 6 + 4 = 10
    - 5-я итерация: 10 + 5 = 15
---
## Пример №2

```js
const people = [
  { name: "Alice", age: 25 },
  { name: "Bob", age: 30 },
  { name: "Charlie", age: 25 },
];

const groupedByAge = people.reduce((acc, person) => {
  const age = person.age;
  if (!acc[age]) {
    acc[age] = [];
  }
  acc[age].push(person.name);
  return acc;
}, {});

console.log(groupedByAge);
// { 25: ["Alice", "Charlie"], 30: ["Bob"] }
```
---
## Пример №3

```js
const numbers = [10, 5, 30, 8, 20];

const max = numbers.reduce((acc, currentValue) => {
  return currentValue > acc ? currentValue : acc;
});

console.log(max); // 30
```
---