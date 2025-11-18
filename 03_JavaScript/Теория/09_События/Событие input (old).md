## Описание

Событие input срабатывает **каждый раз, когда пользователь изменяет содержимое поля ввода** (`<input>`, `<textarea>` и т. д.).

---
## Синтаксис

```js
element.addEventListener("input", function(event) {
    console.log("Введён текст:", event.target.value);
});
```

<font color="#409CFF">`fas:InfoCircle`</font> event.target.value — получает текущее значение поля.

---
## Пример №1: Обновление текста в реальном времени

```html
<input type="text" id="username" placeholder="Введите имя">
<p>Вы ввели: <span id="output">?</span></p>
```

```js
document.querySelector("#username").addEventListener("input", function(event) {
    document.querySelector("#output").textContent = event.target.value;
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- input срабатывает **каждый раз**, когда пользователь вводит символ.
- Текст сразу же отображается в `<span id="output">`.

---
## Пример №2: Валидация в реальном времени

Проверяем длину имени (минимум 3 символа)

```html
<input type="text" id="nameInput" placeholder="Введите имя">
<p id="message"></p>
```

```js
document.querySelector("#nameInput").addEventListener("input", function(event) {
    let value = event.target.value;
    if (value.length < 3) {
        document.querySelector("#message").textContent = "Имя слишком короткое!";
    } else {
        document.querySelector("#message").textContent = "✔ Имя подходит";
    }
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- При вводе проверяется длина текста.
- Если символов меньше 3, показываем ошибку.
- Если больше — выводим “✔ Имя подходит”.

---
## Пример №3: Запрет ввода чисел (только буквы)

Запрещаем вводить цифры в текстовое поле

```html
<input type="text" id="onlyText" placeholder="Введите текст">
<p id="error"></p>
```

```js
document.querySelector("#onlyText").addEventListener("input", function(event) {
    let value = event.target.value;
    if (/\d/.test(value)) { // Проверяем, есть ли в тексте цифры
        document.querySelector("#error").textContent = "❌ Нельзя вводить цифры!";
        event.target.value = value.replace(/\d/g, ""); // Удаляем цифры
    } else {
        document.querySelector("#error").textContent = "";
    }
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- `/\d/`проверяет, есть ли цифры в тексте.
- Если есть, удаляем их с помощью `.replace(/\d/g, "")`.

---
## Пример №4: input для range (ползунок)

Показываем значение ползунка в реальном времени

```html
<input type="range" id="slider" min="0" max="100">
<p>Значение: <span id="value">50</span></p>
```

```js
document.querySelector("#slider").addEventListener("input", function(event) {
    document.querySelector("#value").textContent = event.target.value;
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- При каждом движении ползунка обновляется текст со значением.

---
## Пример №5: Фильтр поиска (поиск по списку)

Фильтруем список по введённому тексту

```html
<input type="text" id="search" placeholder="Поиск...">
<ul id="list">
    <li>Яблоко</li>
    <li>Банан</li>
    <li>Груша</li>
    <li>Апельсин</li>
</ul>
```

```js
document.querySelector("#search").addEventListener("input", function(event) {
    let filter = event.target.value.toLowerCase();
    document.querySelectorAll("#list li").forEach(function(item) {
        item.style.display = item.textContent.toLowerCase().includes(filter) ? "" : "none";
    });
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- При вводе фильтруем элементы списка.
- Если текст совпадает, элемент остаётся видимым.
- Если не совпадает, скрываем (display: none).

---
## Разница между [[Событие change|change]] и input

Иногда вместо change можно использовать input, который срабатывает сразу при изменении значения.

<font color="#409CFF">`fas:InfoCircle`</font> Главное отличие от change:

- input срабатывает **мгновенно**, при каждом изменении.
- change срабатывает **только когда пользователь закончил ввод и ушел с поля (например, нажал Tab или кликнул в другое место).**

```html
<input type="text" id="username" placeholder="Введите имя">
<p>Вы ввели: <span id="output">?</span></p>
```

```js
document.querySelector("#username").addEventListener("change", function(event) {
    console.log("CHANGE:", event.target.value);
});

document.querySelector("#username").addEventListener("input", function(event) {
    console.log("INPUT:", event.target.value);
});
```

📌 **Вывод:**

- Если нужно отслеживать изменение сразу — `input`.
- Если нужно дождаться, когда пользователь закончит ввод — `change`.

---
## ИТОГ:

📌 input срабатывает при каждом изменении поля ввода.
📌 Работает с input, textarea, range и др.
📌 Не подходит для checkbox и radio, там лучше использовать change.
📌 Позволяет делать поиск в реальном времени, валидацию, фильтрацию и многое другое.

  🚀 **Используйте** input**, когда нужно обновлять данные мгновенно!**