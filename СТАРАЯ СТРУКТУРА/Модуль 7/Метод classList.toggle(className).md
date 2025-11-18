Метод работает как переключатель:

- если класс className отсутствует, то добавляет его в конец списка классов
- и наоборот, если класс className присутствует - удаляет его

### Синтаксис:

```js
classList.toggle(className)
```

`className` - Строка с именем класса <font color="#f71735">`ris:Alert`</font> без точки и в скобках `""`

---
### Пример:

```html
<a class="link" href="https://goit.global">GoIT</a>
```

```js
const link = document.querySelector(".link");

link.classList.toggle("is-active");
console.log(link.classList); 
// ["link", "is-active", length: 2, value: "link is-active"]
```

---