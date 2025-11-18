Функция – это независимый блок кода, который выполняет определенную задачу с разными начальными значениями.
Функцию можно представить как черный ящик, который принимает данные на входе и возвращает результат на выходе после выполнения кода внутри функции.

![[Pasted image 20241215033503.png]]

---
## Синтаксис

```js
function имяФункции(параметры) {
  // Тело функции
  return результат;
}
```

Тело функции содержится в фигурных скобках `{}`. Оно содержит инструкции, которые необходимо выполнить при вызове функции.

---
## Вызов функции

```js
// Объявление функции multiply
function doStuff() {
  // Тело функции
  console.log('Log inside multiply function');
}

// Вызовы функции multiply
doStuff(); // 'Log inside multiply function'
doStuff(); // 'Log inside multiply function'
doStuff(); // 'Log inside multiply function'

```

---
## Передача параметров и аргументов

В круглых скобках после имени функции указываются настройки. Параметры являются перечислением данных, ожидаемых функцией во время вызова.

```js
// Объявление параметров x, y, z
function multiply(x, y, z) {
  console.log(`Result: ${x * y * z}`);
}
```

- Параметри — это локальные переменные, доступные только внутри тела функции.
- Аргументы — это то что мы передаём функции когда вызываем её

```js
// Объявление параметров x, y, z
function multiply(x, y, z) {
  console.log(`Result: ${x * y * z}`);
}

// Передача аргументов
multiply(2, 3, 5); // "Result: 30"
multiply(4, 8, 12); // "Result: 384"
multiply(17, 6, 25); // "Result: 2550"
```

Когда мы передаём аргументы должна соблюдаться последовательность порядка.

![[Pasted image 20241215035746.png]]

---
## Return

Оператор `return` используется для возврата значения из тела функции обратно в код в место ее вызова.

```js
function multiply(x, y, z) {
	const product = x * y * z;
  // Повертаємо результат виразу множення
  return product;
}

// Результат роботи функції можна зберегти у змінну
const result = multiply(2, 3, 5);
console.log(result); // 30
```

Чтобы облегчить себе жизнь можно сразу записать результат в оператор `return`, без необходимости создавать ещё одну переменную

```js
function multiply(x, y, z) {
  return x * y * z;
}

const result = multiply(2, 3, 5);
console.log(result); // 30
```

---

Если в теле функции нет оператора возврата то функция ничего не вернёт и консоль выведет `// undefined`

```js
function multiply(x, y, z) {
	const product = x * y * z;
}

const result = multiply(2, 3, 5);
console.log(result); // undefined
```

---

<font color="#fcb97d">`ris:Question`</font>Все инструкции в теле функции после оператора `return` не будут задействованы

```js
function multiply(x, y, z) {
  ✅ console.log('The code before return is executed as usual');

  return x * y * z;

  ❌ console.log('This code is never executed because it is after return');
}

console.log(multiply(2, 3, 5)); // 30
```

---

Область видимости функции

Область видимости означает где функция видит переменные а где нет.

- Глобальными переменные - это те что находятся вне каких либо блоков кода или функций
- Локальная область видимости - это та что используется внутри фигурных скобок {} (условия, циклы, функции и т.п.)

```js
// Глобальная переменная
const value = "I'm a global variable";

function foo() {
// Можно обратиться к глобальной переменной
	console.log(value); // "I'm a global variable"
}

foo();
// Можно обратиться к глобальной переменной
console.log(value); 
// "I'm a global variable"
```

```js
function foo() {
	// Локальна змінна
	const value = "I'm a local variable";
	// Можна звернутися до локальної змінної
	console.log(value); // "I'm a local variable"
}

foo();
console.log(value); // ReferenceError: value is not defined
                    // Помилка: локальну змінну не видно за межами                       функції
```

---