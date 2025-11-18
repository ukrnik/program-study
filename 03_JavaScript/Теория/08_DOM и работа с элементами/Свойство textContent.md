Свойство textContent возвращает все текстовое содержание в элементах (собственные и прикрепленные элементы).

```html
<p class="text">Username: <span class=”sub-text”>Mango</span></p>
```

```js
const el = document.querySelector(".text")
const nested = document.querySelector(".sub-text")

console.log(el.textContent); // "Username: Mango"
console.log(nested.textContent); // "Mango"
```

Также мы можем менять текст внутри тегов

```js
const el = document.querySelector(".text")
console.log(el.textContent); // "Username: Mango"
el.textContent = "Username: Poly";
console.log(el.textContent); // "Username: Poly"
```


![[Снимок экрана 2025-01-07 в 01.15.21.png]]