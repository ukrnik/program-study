Метод принимает один аргумент — строку nameAttribute с именем атрибута, который нужно удалить из указанного HTML-элемента element — и удаляет его.

```html
<img class="image" src="https://picsum.photos/id/15/320/240" alt="Rocks and waterfall" width="300" />
```

```js
const image = document.querySelector(".image");
image.removeAttribute("alt");
console.log(image.hasAttribute("alt")); // false
```
