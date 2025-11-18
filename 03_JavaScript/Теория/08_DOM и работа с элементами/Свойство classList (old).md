## ClassList – это свойство элемента, которое предоставляет удобный способ управления его классами (значениями атрибута class).

**Особенности:**
- Позволяет добавлять, удалять, проверять и переключать классы.
- Удобен для работы с [[CSS-класс|CSS-классами]] без необходимости переписывать всю строку с классами вручную.

По сути помогает нам работать с классам в элементах HTML

```html
<a class="link is-active" href="https://goit.global">GoIT</a>
```

```js
const link = document.querySelector(".link");
console.log(link.classList); 
// ["link", "is-active", length: 2, value: "link is-active"]
```

![[Снимок экрана 2025-01-07 в 01.44.20.png|400]]

Доступ к масиву и отдельным названиям классов нужно получать через индекс '[ ]'


```js
console.log(link.classList[1]); // "is-active"
```


---

- свойство value содержит точное значение атрибута
- свойство length — количество классов у элемента

Но их нужно запрашивать отдельно:

```js
console.log(link.classList.value); //"link is-active"
console.log(link.classList.length); //2
```

---
## Основные методы classList:

| [[Метод classList.contains(className)]]<br>             | Проверка наличия класса в элементе                   |
| ------------------------------------------------------- | ---------------------------------------------------- |
| [[Метод classList.add(className)]]                      | Добавляет класс к элементу                           |
| [[Метод classList.remove(className)]]<br>               | Удаляет класс из элемента                            |
| [[Метод classList.toggle(className)]]                   | В зависимости от наличия удаляет или добавляет класс |
| [[Метод classList.replace(oldClassName, newClassName)]] | Меняет старый класс на новый                         |
