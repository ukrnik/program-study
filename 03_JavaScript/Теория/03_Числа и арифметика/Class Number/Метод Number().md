Возвращает результат в виде числа

```js
console.log(Number("5")); // 5
console.log(Number(true)); // 1
console.log(Number(false)); // 0
console.log(Number(null)); // 0
```

- `true` всегда приводится к 1;
- `false`, `null` и `""` всегда приводятся к 0.

<font color="#f71735">`ris:Alert`</font> Если это не число то выводиться <font color="#f71735">NaN</font>

```js
console.log(Number(undefined)); // NaN
console.log(Number("Jacob")); // NaN
console.log(Number("25px")); // NaN
```

---

Арифметические операции `(+, -, *, /)` выполняют неявное преобразование типов.

```js
console.log("5" * 2); // 10
console.log("10" - 5); // 5
console.log(5 + true); // 6
console.log(5 - true); // 4
```

---

При использовании операторов сравнения `(<, >, <=, >=)` также выполняется неявное преобразование типов. Если операнды разных типов, то перед сравнением они приводятся в число.

```js
console.log("10" > 5); // true
console.log(10 > "5"); // true
console.log(5 > true); // true
console.log(5 < true); // false
console.log("5" < true); // false
```

---