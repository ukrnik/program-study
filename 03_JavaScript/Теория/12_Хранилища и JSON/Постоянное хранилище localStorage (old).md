## Описание

localStorage – это встроенное в браузер хранилище, которое позволяет **сохранять данные на устройстве пользователя** и использовать их даже после перезагрузки страницы.

> [!info]  **Простыми словами:**
> Это как "память" в браузере, где можно хранить настройки, темы, корзину товаров и другие данные.

---
## Как работает localStorage?

- **Данные сохраняются навсегда**, пока пользователь их не удалит вручную или с помощью JavaScript.
- **Максимальный размер хранилища – около 5MB**.
- **Доступно только в браузере**, сервер не получает эти данные.

---
## Когда использовать localStorage?

✔ **Сохранение настроек** (тема, язык, фильтры).  
✔ **Корзина товаров** в интернет-магазине.  
✔ **Запоминание состояния UI** (например, свернутый сайдбар).  
✔ **Сохранение данных формы** (если страница перезагрузится, данные не потеряются).

❌ **Не использовать для чувствительных данных!** (`localStorage` небезопасен и может быть доступен через JavaScript).

---
## Основные методы localStorage

### 1. Просмотр хранилища

```js {3}
localStorage.setItem("username", "Alice");

console.log(localStorage);
// Storage {username: 'Alice', length: 1}
```

<font color="#00b050">`fas:CheckCircle`</font> Теперь в localStorage сохранится ключ `username` со значением `Alice`.

---
### 2. Сохранение данных

```js
localStorage.setItem("username", "Alice");
```

<font color="#00b050">`fas:CheckCircle`</font> Теперь в localStorage сохранится ключ `username` со значением `Alice`.

> [!warning]
>Если в хранилище уже существовала запись с ключом «ui-theme»? 
Вызов метода setItem(key, value) перезапишет его значение.

---
### 3. Получение данных

```js
const user = localStorage.getItem("username");
console.log(user); // Alice
```

---
### 4. Удаление конкретного элемента

```js
localStorage.removeItem("username");
```

---
### 5. Очистка всего хранилища

```js
localStorage.clear();
```

> [!warning]
> После `clear()` **все данные в localStorage удалятся!**

---
## Работа с объектами в localStorage

> [!info]
> `localStorage` хранит **только строки**, поэтому **объекты и массивы нужно преобразовывать** в JSON.

### 1. Сохранение объекта

**Технически в веб-хранилище можно записать только строки.** Но это не проблема, если использовать методы класса **JSON** для преобразования сложных типов.

Если необходимо сохранить **что-то, кроме строки**, например, **массив** или **объект**, необходимо преобразовать их в строку методом **JSON.stringify()**.

```js
const user = { name: "Alice", age: 25 };
localStorage.setItem("user", JSON.stringify(user));
```

```js
const settings = {
  theme: "dark",
  isAuthenticated: true,
  options: [1, 2, 3],
};

localStorage.setItem("settings", JSON.stringify(settings));
```


![[Снимок экрана 2025-03-15 в 23.28.27.png]]


### 2. Чтение объекта

Метод getItem(key) позволяет считать из хранилища запись с ключом key и возвращает ее значение в JSON формате.

```js
const userData = JSON.parse(localStorage.getItem("user"));
console.log(userData.name); // Alice
```

<font color="#409CFF">`fas:InfoCircle`</font> Теперь `userData` – это объект, с которым можно работать.

> [!warning]
> Якщо у сховищі відсутній запис з таким ключем, метод повертає `**null**`.

```js
const savedItem = localStorage.getItem("key-that-does-not-exist"); 
console.log(savedItem); // null
```

<font color="#409CFF">`fas:InfoCircle`</font> Если значение является примитивным типом, нет необходимости его парсить.

В противном случае, если это массив или объект, необходимо распарсить значение методом [[Формат JSON|JSON.parse()]], чтобы получить валидные данные.

```js
const settings = {
  theme: "dark",
  isAuthenticated: true,
  options: [1, 2, 3],
};
localStorage.setItem("settings", JSON.stringify(settings));

const savedSettings = localStorage.getItem("settings");
console.log(savedSettings); // A string

const parsedSettings = JSON.parse(savedSettings);
console.log(parsedSettings); // Settings object
```

> [!info]
> У змінній `savedSettings` буде рядок, що представляє об'єкт, тому ми розпарсюємо це значення, і у змінній `parsedSettings` отримуємо повноцінний об'єкт із властивостями.
### 3. Удаление данных

Метод `removeItem(key)` удаляет из хранилища существующую запись с ключом `key`. В результате своей работы он не возвращает значение.

```js
localStorage.setItem("ui-theme", "dark");
console.log(localStorage.getItem("ui-theme")); // "dark"

localStorage.removeItem("ui-theme");
console.log(localStorage.getItem("ui-theme")); // null
```

---
## Проверка наличия данных в localStorage

<font color="#e36c09">`ris:Alert`</font> Иногда нужно проверить, есть ли данные в хранилище:

```js
if (localStorage.getItem("user")) {
    console.log("Данные есть!");
} else {
    console.log("Данных нет!");
}
```

> [!done]
> Если ключ `user` существует, выведется `Данные есть!`.

---

## ИТОГ:

✔ `localStorage` – это браузерное хранилище, данные которого **сохраняются навсегда**. 
✔ Доступ к данным возможен **только с клиентской стороны**.  
✔ Данные хранятся в виде **строк**, но можно использовать `JSON.stringify()` и `JSON.parse()`.  
✔ Подходит для **настроек, сохраненных данных форм, корзины товаров** и других вещей, которые нужно хранить **локально**.
