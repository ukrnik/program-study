Используется только если нужно найти один, чаще всего уникальный элемент

```js
element.querySelector(selector)
```

- Возвращает первый найденный элемент внутри element, соответствующий строке [[CSS-Selector|CSS-селектора]] selector. Даже если их несколько, всегда вернется ссылка на первый элемент в [[DOM|DOM-дереве]].
- Если ничего не найдено, то вернет null

![[Pasted image 20241217005205.png]]

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
const firstMenuItem = document.querySelector(".menu-item");
console.log(firstMenuItem);

// <li class="menu-item">home</li>
```