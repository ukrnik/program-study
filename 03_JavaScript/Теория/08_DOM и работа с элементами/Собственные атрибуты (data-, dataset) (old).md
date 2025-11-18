**Собственные атрибуты** (custom attributes) — это специальные атрибуты, которые вы можете добавлять к HTML-элементам, чтобы сохранять дополнительную информацию, связанную с этими элементами. Они полезны, когда стандартных атрибутов, определённых спецификацией HTML, недостаточно для решения задач.

Самыми популярными среди собственных атрибутов являются **data-атрибуты**, которые используются для передачи данных в JavaScript.

```html
<button type="button" data-action="save">Save text</button>
<button type="button" data-action="close">Close editor</button>
```

---
## Получение значений

Для получения значения data-атрибута используется свойство dataset, после которого через точку пишется имя атрибута без data-. То есть data- отвергается, а другая часть имени записывается как имя свойства объекта.

```js
const saveBtn = document.querySelector('button[data-action="save"]');
console.log(saveBtn.dataset.action); // "save"

const closeBtn = document.querySelector('button[data-action="close"]');
console.log(closeBtn.dataset.action); // "close"
```

---
## Изменение значений

Изменить значение существующего data-атрибута или добавить новый можно так же, как и любому другому свойству объекта в JavaScript. Чтобы это сделать, необходимо получить доступ к DOM-элементу, а затем изменить/задать значение свойства в объекте dataset.

```js
// Змінюємо значення data-action для кнопки saveBtn
saveBtn.dataset.action = "update";

// Додаємо новий data-атрибут data-role
saveBtn.dataset.role = "admin";

// Перевіримо нові значення
console.log(saveBtn.dataset.action); // "update"
console.log(saveBtn.dataset.role); // "admin"
```

---