Метод ожидает аргумента строки с именем класса и добавляет класс className в список классов элемента.

### Синтаксис:

```js
classList.add(className)
```

`className` - Строка с именем класса <font color="#f71735">`ris:Alert`</font> без точки и в скобках `""`

---
### Пример:

```html
<a class="link is-active" href="https://goit.global">GoIT</a>
```

```js
const link = document.querySelector(".link");

link.classList.add("special");
console.log(link.classList); 
// ["link", "is-active", "special", length: 3, value: "link is-active special"]
```

![[Снимок экрана 2025-01-07 в 02.00.39.png|400]]

---

<font color="#fcb97d">`ris:Question`</font> Можно добавлять более одного класса, указав несколько аргументов через запятую.

### Пример:

```html
<a class="link is-active" href="https://goit.global">GoIT</a>
```

```js
const link = document.querySelector(".link");

link.classList.add("special", "hello", "usuall");
console.log(link.classList); 
// ["link", "is-active", "special", length: 5, value: "link is-active special hello usuall"]
```

![[Снимок экрана 2025-01-07 в 02.00.01.png|400]]

---