Метод `Number.parseFloat()` аналогичен [методу Number.parseInt()](Метод Number.parseInt()) с одним отличием: превращает строку в число с плавающей точкой.

```js
console.log(Number.parseFloat("5")); // 5
console.log(Number.parseFloat("5.5")); // 5.5
console.log(Number.parseFloat("3.14")); // 3.14
console.log(Number.parseFloat("5cm")); // 5
console.log(Number.parseFloat("5.5cm")); // 5.5
console.log(Number.parseFloat("12qwe74")); // 12
console.log(Number.parseFloat("12.46qwe79")); // 12.46
console.log(Number.parseFloat("cm5")); // NaN
console.log(Number.parseFloat("")); // NaN
console.log(Number.parseFloat("qweqwe")); // NaN
```

<font color="#f71735">`ris:Alert`</font> Если первые символы строки не могут быть преобразованы в число, или строка пуста или отсутствует, результатом будет значение <font color="#f71735">NaN</font>