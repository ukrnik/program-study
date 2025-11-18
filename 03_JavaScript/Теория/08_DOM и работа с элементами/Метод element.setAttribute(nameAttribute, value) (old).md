Метод принимает два аргумента: строку nameAttribute с именем атрибута, который нужно установить или изменить, и value со значением, которое нужно атрибуту присвоить. Метод устанавливает или изменяет значение указанного атрибута для указанного элемента HTML.

```html
<img class="image" src="https://picsum.photos/id/15/320/240" alt="Rocks and waterfall" width="300" />
```

```js
const image = document.querySelector(".image");
image.setAttribute("alt", "Amazing nature");
console.log(image.getAttribute("alt")); // Amazing nature
```
