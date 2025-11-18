Свойство style в JavaScript используется для управления стилями HTML-элементов через объект [[DOM]]. Оно позволяет изменять CSS-свойства элемента непосредственно с помощью JavaScript.

1. Все CSS-свойства, которые пишутся через дефис, преобразуются в camelCase:
	- background-color → backgroundColor
	- font-size → fontSize
	- margin-top → marginTop
2. Для CSS-переменных и случаев, где важно сохранить оригинальную запись, используйте [[setProperty]] или [[getPropertyValue]].

```js
const button = document.querySelector(".btn");

button.style.backgroundColor = "teal";
button.style.fontSize = "24px";
button.style.textAlign = "center";

console.log(button.style); // inline styles object
```

<font color="#fcb97d">`ris:Question`</font> На практике стилизация элементов обычно производится путем добавления CSS-классов.

<font color="#f71735">`ris:Alert`</font> Свойство style используется для добавления любых динамических стилей, например если ссылка на фоновое изображение неизвестно заранее и приходит с бэкенда.
### Итог:

Свойство style — это удобный способ манипулировать стилями элемента напрямую через JavaScript. Однако для сложных изменений лучше использовать классы CSS и методы работы с ними (classList.add, classList.remove).