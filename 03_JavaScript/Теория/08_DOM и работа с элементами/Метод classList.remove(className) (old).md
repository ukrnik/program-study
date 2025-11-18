Метод удаляет класс className из списка классов элемента.
### Синтаксис:

```js
classList.remove(className)
```

`className` - Строка с именем класса <font color="#f71735">`ris:Alert`</font> без точки и в скобках `""`

---
### Пример:

```html
<a class="link is-active" href="https://goit.global">GoIT</a>
```

```js
const link = document.querySelector(".link");

link.classList.remove("is-active");
console.log(link.classList); 
// ["link", length: 1, value: "link"]
```

<font color="#f71735">`ris:Alert`</font> Если попробовать удалить класс которого нет у элемента то ничего не произойдет

---