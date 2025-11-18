_В JavaScript объект console предоставляет множество методов для вывода информации в консоль браузера или среды выполнения_
## console.time() и console.timeEnd() - Измеряют время выполнения кода.

```js
console.time("Timer");
for (let i = 0; i < 1000000; i++) {} // Простая задержка
console.timeEnd("Timer");
```

---
## console.clear() - Очищает консоль.

```js
console.clear();
```

---

## console.dir() - Выводит интерактивное представление объекта (в виде дерева).

```js
const user = { name: "Alice", age: 30 };
console.dir(user);
```

---

## console.log() - Используется для вывода стандартных сообщений в консоль. Можно выводить строки, числа, объекты, массивы и другие типы данных.

```js
console.log("Hello, World!");
console.log({ name: "John", age: 25 });
```

---

## console.table() - Представляет массивы или объекты в виде таблицы. Очень удобно для визуализации данных в удобочитаемом формате.

```js
const users = [
  { name: "Alice", age: 30 },
  { name: "Bob", age: 25 },
];
console.table(users);
```

---
