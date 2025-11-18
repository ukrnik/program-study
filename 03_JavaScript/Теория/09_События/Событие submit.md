## Описание

Событие submit срабатывает, когда пользователь **отправляет форму** `<form>`. Оно возникает при нажатии на кнопку Submit `<button type="submit">` или при нажатии Enter внутри поля ввода.

<font color="#f71735">`ris:Alert`</font> Событие submit работает **только с формами** `<form>`, а не с отдельными кнопками!

<font color="#f71735">`ris:Alert`</font> По умолчанию при отправке формы браузер перезагружает страницу.

---
## Синтаксис

```js
const form = document.querySelector("form");

form.addEventListener("submit", event => {
	// ...
});
```

---
## Как использовать событие submit?

### Пример: Отслеживание отправки формы

```js
document.querySelector("form").addEventListener("submit", function(event) {
    event.preventDefault(); // Останавливаем стандартную отправку формы
    console.log("Форма отправлена!");
});
```

<font color="#fcb97d">`ris:Question`</font> Что здесь происходит?

1. Находим `<form>` и вешаем на неё addEventListener("submit").
2. event.preventDefault() **отменяет стандартную отправку** (чтобы страница не перезагружалась).
3. Выводим сообщение "Форма отправлена!" в консоль.

---
## Пример №1 Как отменить перезагрузку страницы при отправке формы

Чаще это поведение нежелательно и его необходимо отменить. Для отмены действия браузера по умолчанию объекта события есть стандартный метод `preventDefault()`.

```js
const form = document.querySelector("form");

form.addEventListener("submit", event => {
	event.preventDefault();
});
```


---
## Пример №2 Как получить данные из формы?

Собираем данные из полей формы

```html
<form id="myForm">
    <input type="text" name="username" placeholder="Введите имя">
    <input type="email" name="email" placeholder="Введите email">
    <button type="submit">Отправить</button>
</form>
```

```js
document.querySelector("#myForm").addEventListener("submit", function(event) {
    event.preventDefault(); // Останавливаем отправку

    // Получаем данные из полей
    const username = event.target.username.value;
    const email = event.target.email.value;

    console.log("Имя:", username);
    console.log("Email:", email);
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- event.target — это сама форма.
- event.target.username.value — получаем значение поля с name="username".
- event.target.email.value — получаем значение поля с name="email".
- Теперь можно отправить данные на сервер, проверить их или использовать в коде.

---
## Пример №3 Как проверить, что все поля заполнены?

Валидация перед отправкой

```html
<form id="myForm">
    <input type="text" name="username" placeholder="Введите имя">
    <input type="email" name="email" placeholder="Введите email">
    <button type="submit">Отправить</button>
</form>
```

```js
document.querySelector("#myForm").addEventListener("submit", function(event) {
    event.preventDefault();

    const username = event.target.username.value.trim();
    const email = event.target.email.value.trim();

    if (username === "" || email === "") {
        alert("Заполните все поля!");
        return;
    }

    console.log("Форма успешно отправлена!", { username, email });
});
```

<font color="#fcb97d">`ris:Question`</font> Как это работает?

- `.trim()` убирает пробелы в начале и конце строки.
- Если поле пустое, выводим `alert()` и останавливаем отправку.
- Если всё заполнено, данные отправляются.

---
## Пример №4 Проверка полей + сброс формы

```html
<form class="form" autocomplete="off">
  <input type="text" name="login" placeholder="Login">
  <input type="password" name="password" placeholder="Password">
  <button class="btn" type="submit">Register</button>
</form>
```

```js
const registerForm = document.querySelector(".form");

registerForm.addEventListener("submit", handleSubmit);

function handleSubmit(event) {
  event.preventDefault();
  const form = event.target;
  const login = form.elements.login.value;
  const password = form.elements.password.value;
  
  if (login === "" || password === "") {
    return console.log("Please fill in all the fields!");
  }

  console.log(`Login: ${login}, Password: ${password}`);
  form.reset();
}

```

<font color="#409CFF">`fas:InfoCircle`</font> form.reset(); - сбрасывает текст в полях формы

---
## ИТОГ:

  📌 Событие `submit` позволяет **отслеживать отправку формы, получать данные из полей и отправлять их на сервер без перезагрузки страницы**.
