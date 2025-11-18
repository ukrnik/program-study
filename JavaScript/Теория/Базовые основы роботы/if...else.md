## Описание

**if...else** — это **основная конструкция** для выполнения **условных операций** в JavaScript.

---
## Синтаксис if...else:

```js
if (условие) {
  // Выполнится, если условие истинно (true)
} else {
  // Выполнится, если условие ложно (false)
}
```

---
## Синтаксис if...else if...else

```js
const score = 75;

if (score >= 90) {
  console.log("Отлично");
} else if (score >= 75) {
  console.log("Хорошо");
} else if (score >= 50) {
  console.log("Удовлетворительно");
} else {
  console.log("Неудовлетворительно");
}
```

- Проверяется первое условие (score >= 90).
- Если false, переходит к следующему (score >= 75).
- Если одно из условий истинно (true), остальные **не проверяются**.
---
## Синтаксис Вложенные if...else

```js
const age = 20;
const isMember = true;

if (age >= 18) {
  if (isMember) {
    console.log("Скидка для членов клуба");
  } else {
    console.log("Скидка не предоставляется");
  }
} else {
  console.log("Слишком молоды");
}
```

---