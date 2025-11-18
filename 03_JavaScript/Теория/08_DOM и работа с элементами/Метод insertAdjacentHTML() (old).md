Метод insertAdjacentHTML() используется для добавления HTML-кода в определённое место относительно элемента. Этот метод позволяет вставить строку HTML как HTML-код (а не текст), что делает его удобным и эффективным для манипуляции DOM.

## Синтаксис

```js
element.insertAdjacentHTML(position, text);
```

- element: элемент, к которому применяется метод.
- position: строка, указывающая позицию, куда вставить HTML. Принимает следующие значения:
	- "beforebegin": перед самим элементом element.
	- "afterbegin": в начало element (внутрь элемента перед его первым потомком).
	- "beforeend": в конец element (внутрь элемента после его последнего потомка).
	- "afterend": сразу после element.
- text: строка с HTML-кодом, который нужно вставить.

![[Pasted image 20250115020723.png]]

---

<font color="#f71735">`ris:Alert`</font> <font color="#f71735">Значения "beforebegin" и "afterend" для метода insertAdjacentHTML() работают только в том случае, если целевой элемент уже добавлен в DOM-дерево.</font>

### Механизм работы beforebegin **и** afterend:

Значения "beforebegin" и "afterend" предполагают добавление HTML вне целевого элемента:

- "beforebegin" — перед началом элемента.
- "afterend" — сразу после окончания элемента.

Если элемент ещё не находится в DOM-дереве, браузер не знает, где именно находится этот элемент относительно других узлов, и не может вычислить, куда вставить HTML-код. Поэтому метод не сработает.

---
## Пример 1

```html
<div id="myDiv">
    <p>Это существующий параграф.</p>
</div>
<button id="addHTMLButton">Добавить HTML</button>
```

```js
// Получаем элементы
const divElement = document.getElementById("myDiv");
const addHTMLButton = document.getElementById("addHTMLButton");

// Добавляем обработчик события на кнопку
addHTMLButton.addEventListener("click", () => {
    // Вставляем HTML-код в разные места
    divElement.insertAdjacentHTML("beforebegin", "<p>HTML перед div.</p>");
    divElement.insertAdjacentHTML("afterbegin", "<p>HTML в начале div.</p>");
    divElement.insertAdjacentHTML("beforeend", "<p>HTML в конце div.</p>");
    divElement.insertAdjacentHTML("afterend", "<p>HTML после div.</p>");
});
```

---
## Пример 2


```html
<ul class="list">
  <li class="list-item">HTML</li>
  <li class="list-item">CSS</li>
  <li class="list-item">JavaScript</li>
</ul>
```

```js
const list = document.querySelector(".list");

const newTechnologies = ["React", "TypeScript", "Node.js"];
const markup = newTechnologies
  .map((technology) => `<li class="list-item new">${technology}</li>`)
  .join("");

list.insertAdjacentHTML("beforeend", markup);
list.insertAdjacentHTML("beforebegin", "<h2>Popular technologies</h2>");
```

![[Снимок экрана 2025-01-15 в 02.17.25.png|400]]

---
## Объяснение работы:

1. Изначально:
```html
<div id="myDiv">
    <p>Это существующий параграф.</p>
</div>
<button id="addHTMLButton">Добавить HTML</button>
```

2. После нажатия кнопки:
HTML внутри и вокруг `<div>` изменится:

```html
<p>HTML перед div.</p>
<div id="myDiv">
    <p>HTML в начале div.</p>
    <p>Это существующий параграф.</p>
    <p>HTML в конце div.</p>
</div>
<p>HTML после div.</p>
<button id="addHTMLButton">Добавить HTML</button>
```

---
## Плюсы insertAdjacentHTML():

- Вставляет строку HTML без удаления существующего содержимого.
- Быстрее, чем innerHTML, поскольку не трогает парсинг и пересоздание DOM-узла целиком.

---