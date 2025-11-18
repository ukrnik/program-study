## Описание

<font color="#409CFF">`fas:InfoCircle`</font> Событие `change` срабатывает, когда пользователь изменяет значение элемента формы (например, текстового поля, чекбокса, выпадающего списка) и уходит с него (например, переключается на другой элемент).

- Для текстовых полей (`<input type="text">`, `<textarea>`) событие происходит, когда фокус уходит с поля.

- Для чекбоксов, радио-кнопок и выпадающих списков (`<select>`, `<input type="checkbox">`, `<input type="radio">`) — сразу после изменения.

---
## Пример №1: Отслеживаем изменение текста в input

```html
<input type="text" id="username" placeholder="Введите имя">
<p>Ваше имя: <span id="output">?</span></p>
```

```js
document.querySelector("#username").addEventListener("change", function(event) {
    document.querySelector("#output").textContent = event.target.value;
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

1. Пользователь вводит текст в поле.
2. Когда он **переключается** на другой элемент (например, нажимает Tab или кликает в другое место), срабатывает change.
3. Введённый текст отображается в `<span id="output">`.

---
## Когда срабатывает change?

| Элемент                                           | Когда срабатывает change?                      |
| ------------------------------------------------- | ---------------------------------------------- |
| `<input type="text">`, `<textarea>`               | Когда пользователь закончил ввод и ушёл с поля |
| `<select>` (выпадающий список)                    | Когда выбрали другой пункт                     |
| `<input type="checkbox">`, `<input type="radio">` |  Сразу после изменения состояния (вкл/выкл)    |

---
## Пример №2: Событие change для выпадающего списка (select)

```html
<select id="city">
    <option value="moscow">Москва</option>
    <option value="spb">Санкт-Петербург</option>
    <option value="kazan">Казань</option>
</select>
<p>Вы выбрали: <span id="selected-city">?</span></p>
```

```js
document.querySelector("#city").addEventListener("change", function(event) {

    document.querySelector("#selected-city").textContent = event.target.value;
   });
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- При выборе нового города событие `change` сразу срабатывает.
- `event.target.value` получает значение (`value`) выбранного пункта.

---
## Пример №3: Событие change для чекбокса

```html
<input type="checkbox" id="agree">
<label for="agree">Я согласен с условиями</label>
<p id="message"></p>
```

```js
document.querySelector("#agree").addEventListener("change", function(event) {
	if (event.target.checked) {
		document.querySelector("#message").textContent = "✅ Вы согласились!";
	} else {
		document.querySelector("#message").textContent = "❌ Вы не согласны.";
	}
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- `event.target.checked` возвращает `true`, если чекбокс включён, и `false`, если выключен.
- При каждом клике состояние меняется, и сразу же срабатывает `change`.

---
## Пример №4: Событие change для радио-кнопок

```html
<label><input type="radio" name="gender" value="male"> Мужчина</label>
<label><input type="radio" name="gender" value="female"> Женщина</label>
<p>Вы выбрали: <span id="selected-gender">?</span></p>
```

```js
document.querySelectorAll('input[name="gender"]').forEach(function(radio) {
    radio.addEventListener("change", function(event) {
        document.querySelector("#selected-gender").textContent = event.target.value;
    });
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- `querySelectorAll()` выбирает все радио-кнопки с `name="gender"`.
- `forEach()` добавляет change на каждую радио-кнопку.
- Как только пользователь выбирает Мужчина или Женщина, текст меняется.

---
## Пример №5:Событие change для input type="file"

```html
<input type="file" id="fileInput">
<p>Выбранный файл: <span id="fileName">Нет файла</span></p>
```

```js
document.querySelector("#fileInput").addEventListener("change", function(event) {
    let file = event.target.files[0]; // Получаем первый выбранный файл
    document.querySelector("#fileName").textContent = file ? file.name : "Нет файла";
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- `event.target.files[0]` получает **первый выбранный файл**.
- Если файл выбран, показываем его **имя** `(file.name)`.
- Если файла нет, показываем "Нет файла".

---
## Разница между change и [[Событие input|input]]

Иногда вместо change можно использовать input, который срабатывает сразу при изменении значения.

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

📌 `change` срабатывает, когда пользователь изменил значение и покинул поле.
📌 Работает с `input`, `textarea`, `select`, `checkbox`, `radio`, `file`.
📌 Для `text` и `textarea` событие `change` срабатывает только после ухода с поля.
📌 Для checkbox, radio, select и file — сразу при изменении.
📌 Если нужно отслеживать ввод в реальном времени, используйте input.