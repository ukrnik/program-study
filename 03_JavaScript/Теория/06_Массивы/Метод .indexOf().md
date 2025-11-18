В indexOf() мы передаем значение которое мы хотим узнать индекс в масиве

```js
const courses = ['HTML', 'CSS', 'JavaScript'];

const javascriptIndex = courses.indexOf("JavaScript");
console.log(javascriptIndex); // 2
```

Если такое значения нет в масиве то метод вернёт нам -1

```js
const courses = ['HTML', 'CSS', 'JavaScript'];

const cssIndex = courses.indexOf("React");
console.log(cssIndex); // -1
```