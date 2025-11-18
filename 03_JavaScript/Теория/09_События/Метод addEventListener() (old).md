## Описание

Метод addEventListener() позволяет добавлять обработчики событий к элементам HTML, обеспечивая более гибкий и удобный способ обработки событий по сравнению с атрибутами onclick, onmouseover и т. д.

---
## Синтаксис

```js
element.addEventListener(event, handler, options);
```

- element – элемент, к которому добавляется обработчик события.
- event – название события (например, "click", "mouseover", "keydown", "input" и т. д.).
- handler – [[Функция Function Declaration|функция]] или [[|колбек-функция]], которая будет выполнена при наступлении события.
- options _(необязательный параметр)_ – объект с дополнительными настройками (например, { once: true }).

---
## Пример №1

1. В HTML есть кнопка с классом my-button.

```html
<button class="my-button">Next</button>
```

2. Чтобы галерея листалась, тебе нужно в JavaScript коде получить ссылку на элемент кнопки и добавить на него слушателя события клика.

```js
const button = document.querySelector(".my-button");

button.addEventListener("click", () => {
  console.log("The button was pressed and now the next image will appear");
});
```

Для колбека можно использовать не анонимную, а отдельную функцию, передавая ссылку, как это реализовано в примере ниже. Именуемая функция увеличивает читабельность кода.

```js
const button = document.querySelector(".my-button");

const handleClick = () => {
  console.log("The button was pressed and now the next image will appear");
};

button.addEventListener("click", handleClick);
```


---
## Пример №2

Добавление обработчика клика на кнопку:

```js
const button = document.getElementById("myButton");

button.addEventListener("click", function () {
    alert("Кнопка нажата!");
});
```

---
## Преимущества

<font color="#fcb97d">`ris:Question`</font> 1. Можно добавить несколько обработчиков для одного события

```js
const btn = document.getElementById("myButton");

const firstCallback = () => {
  console.log("Первый обработчик");
};
const secondCallback = () => {
  console.log("Второй обработчик");
};
const thirdCallback = () => {
  console.log("Третий обработчик");
};

btn.addEventListener("click", firstCallback);
btn.addEventListener("click", secondCallback);
btn.addEventListener("click", thirdCallback);
```

`fas:ArrowDown` Вывод в консоль:

```js
"Первый обработчик"
"Второй обработчик"
"Третий обработчик"
```

---

<font color="#fcb97d">`ris:Question`</font> 2. Можно удалить обработчик событий с помощью [[Метод removeEventListener()|removeEventListener()]]

```js
function handleClick() {
    alert("Кнопка нажата!");
}

button.addEventListener("click", handleClick);

// Позже можно удалить обработчик
button.removeEventListener("click", handleClick);
```

<font color="#f71735">`ris:Alert`</font> Обработчик должен быть объявлен как именованная функция^[Именованная функция (named function) — это функция, у которой есть имя, присвоенное в момент её объявления. Она отличается от **анонимной функции**, которая создаётся без имени.]  , иначе [[Метод removeEventListener()|removeEventListener()]] не сможет удалить его.

---
## Примеры работы с различными событиями

1. Клик по элементу

```js
document.getElementById("myDiv").addEventListener("click", function () {
    this.style.backgroundColor = "yellow";
});
```


---

2. Наведение мыши (mouseover и mouseout)

```js
const box = document.getElementById("box");

box.addEventListener("mouseover", function () {
    this.style.backgroundColor = "lightblue";
});

box.addEventListener("mouseout", function () {
    this.style.backgroundColor = "";
});
```


---

3. Отслеживание нажатия клавиши

```js
document.addEventListener("keydown", function (event) {
    console.log(`Вы нажали: ${event.key}`);
});
```


---

4. Отслеживание изменений в поле ввода (input)

```js
const input = document.getElementById("myInput");

input.addEventListener("input", function () {
    console.log("Текущее значение: " + this.value);
});
```


---

[^1]: 