## Описание

Метод removeEventListener() позволяет удалить ранее добавленный обработчик событий, который был привязан с помощью addEventListener(). Это полезно, если обработчик больше не нужен или мешает работе.

---
## Синтаксис

```js
element.removeEventListener(event, handler, options);
```

- element – элемент, с которого удаляется обработчик.
- event – тип события ("click", "keydown", "mouseover" и т. д.).
- handler – ссылка на функцию-обработчик, которую нужно удалить.
- options _(необязательный параметр)_ – объект с дополнительными параметрами (например, { capture: true }), который должен совпадать с параметрами addEventListener().

---
## <font color="#f71735">`ris:Alert`</font> Как правильно использовать removeEventListener()

Чтобы removeEventListener() работал, необходимо передавать **точно ту же функцию**, которая была использована в [[Метод addEventListener()|addEventListener()]].

❌ Неправильный пример (анонимная функция)

```js
const button = document.getElementById("myButton");

// Добавляем обработчик
button.addEventListener("click", function () {
    console.log("Кнопка нажата!");
});

// Попытка удалить обработчик — НЕ СРАБОТАЕТ!
button.removeEventListener("click", function () {
    console.log("Кнопка нажата!");
});
```

<font color="#f71735">`ris:Alert`</font> **Ошибка:** Мы передаём в removeEventListener() другую (новую) анонимную функцию, которая не совпадает с той, что была добавлена.

---

✅ Правильный пример (именованная функция)

```js
const button = document.getElementById("myButton");

function handleClick() {
    console.log("Кнопка нажата!");
}

// Добавляем обработчик
button.addEventListener("click", handleClick);

// Удаляем обработчик
button.removeEventListener("click", handleClick);
```

<font color="#fcb97d">`ris:Question`</font> Теперь всё работает, потому что removeEventListener() передаёт **ту же самую функцию**, что и [[Метод addEventListener()|addEventListener()]].

---

✅ Правильный пример №2

```js
const button = document.querySelector(".my-button");

const handleClick = () => {
  console.log("The button was pressed and now the next image will appear");
};

button.addEventListener("click", handleClick);

```

---
## Пример №1

```html
<button class="btn js-add">Add Listener</button>
<button class="btn js-remove">Remove Listener</button>
<hr>
<button class="btn target-btn">Click me</button>
```

```js
const addListenerBtn = document.querySelector('.js-add');
const removeListenerBtn = document.querySelector('.js-remove');
const btn = document.querySelector(".target-btn");

const handleClick = () => {
  console.log("click event listener callback");
};

addListenerBtn.addEventListener("click", () => {
  btn.addEventListener("click", handleClick);
  console.log("click event listener was added to btn");
});

removeListenerBtn.addEventListener("click", () => {
  btn.removeEventListener("click", handleClick);
  console.log("click event listener was removed from btn");
});
```

<font color="#fcb97d">`ris:Question`</font> Одна кнопка (`addListenerBtn`) добавляет обработчик событий а вторая кнопка (`removeListenerBtn`) удаляет обработчик событий с кнопки (`btn`).

![[Снимок экрана 2025-01-18 в 04.08.55.png|450]]

---