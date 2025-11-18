Помогает нам сделать перевод с псевдомасива в масив

```js
function foo(){
	console.log(arguments); // [1, 2, 3] ❌ нет нужных методов
	
	const realArray = Array.from(arguments);
	
	console.log(realArray); // [1, 2, 3] ✅ это нормальный масив
}

foo(1, 2, 3);
```
