Проверяет наличия класса у элемента HTML и возвращает `true` или `false`.

### Синтаксис:

```js
classList.contains(className);
```

`className` - Строка с именем класса <font color="#f71735">`ris:Alert`</font> без точки и в скобках `""`

---
### Пример:

```html
<a class="link is-active" href="https://goit.global">GoIT</a>
```

```js
const link = document.querySelector(".link");

const hasActiveClass1 = link.classList.contains("is-active"); // true
const hasActiveClass2 = link.classList.contains("title"); // false
```

---