Метод получает один аргумент – строка nameAttribute с именем атрибута, и возвращает значение этого атрибута для указанного HTML-элемента element. Если атрибут не найден, метод возвращает null.

```html
<img class="image" src="https://picsum.photos/id/15/320/240" alt="Rocks and waterfall" width="300" />
```

```js
const image = document.querySelector(".image");
console.log(image.getAttribute("alt")); // "Rocks and waterfall"
```
