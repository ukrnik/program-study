Метод принимает один аргумент - строку nameAttribute, содержащую имя атрибута для проверки и возвращает результат проверки его наличия на элементе element - true или false.

```html
<img class="image" src="https://picsum.photos/id/15/320/240" alt="Rocks and waterfall" width="300" />
```

```js
const image = document.querySelector(".image");
console.log(image.hasAttribute("src")); // true
console.log(image.hasAttribute("href")); // false
```
