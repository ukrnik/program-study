Используем чтобы найти коллекцию элементов. Получаем масив ссылок на элементы з одинаковым селектором.

```js
element.querySelectorAll(selector)
```

- Возвращает [[Псевдомассив|псевдомассив]] всех элементов внутри element, соответствующих [[CSS-Selector|CSS-селектору]] `selector`
- Если ничего не найдено, вернет пустой массив

![[Pasted image 20241217005549.png]]

---
## Пример:


```html
<ul id="menu" class="menu">
  <li class="menu-item">home</li>
  <li class="menu-item">about</li>
  <li class="menu-item">gallery</li>
  <li>blog</li>
</ul>
```


```js 
const listWithId = document.querySelector('#menu');
listWithId.style.textTransform = 'uppercase';
listWithId.style.fontSize = '24px';
console.log(listWithId);

// <ul id="menu" class="menu" style="text-transform: uppercase; font-size: 24px;">
//   <li class="menu-item">home</li>
//   <li class="menu-item">about</li>
//   <li class="menu-item">gallery</li>
//   <li>blog</li>
// </ul>

const listWithClass = document.querySelector('.menu');
console.log(listWithClass);

// <ul id="menu" class="menu" style="text-transform: uppercase; font-size: 24px;">
//   <li class="menu-item">home</li>
//   <li class="menu-item">about</li>
//   <li class="menu-item">gallery</li>
//   <li>blog</li>
// </ul>

const menuItemsByTagName = document.querySelectorAll("li");
console.log(menuItemsByTagName);

// [<li/>,<li/>,<li/>,<li/>]

const menuItemsByClass = document.querySelectorAll(".menu-item");
console.log(menuItemsByClass);

// [<li/>,<li/>,<li/>]

const firstMenuItem = document.querySelector(".menu-item");
firstMenuItem.style.color = 'tomato';
console.log(firstMenuItem);

// <li class="menu-item" style="color: tomato;">home</li>
```

![[Снимок экрана 2024-12-31 в 00.18.20.png|400]]