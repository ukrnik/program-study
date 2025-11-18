Метод ожидает 2 аргумента строки (первый – старое название класса, второй – новое название класса) и заменяет существующий класс oldClassName на указанный newClassName.

### Синтаксис:

```js
classList.replace(oldClassName, newClassName);
```

`oldClassName`и `newClassName` - Строка с именем класса <font color="#f71735">`ris:Alert`</font> без точки и в скобках `""`

---
### Пример:

```html
<a class="link is-active" href="https://goit.global">GoIT</a>
```

```js
const link = document.querySelector(".link");

link.classList.replace("is-active", "regular");
console.log(link.classList); 
// ["link", "regular", length: 2, value: "link regular"]
```

<font color="#f71735">`ris:Alert`</font> Если попытаться изменить класс, которого не существует на элементе, то это не вызовет ошибку. Просто ничего не изменится.

---