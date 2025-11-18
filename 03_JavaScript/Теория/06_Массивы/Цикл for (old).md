Цикл for помогает нам перебрать каждый элемент масива

В данном примере мы передаем в функцию масив array и строку для поиска в масиве friendname, если условие (array[i] === friendname) то мы выводим в консоль текст

```js
const friends = ['Mango', 'Kiwi', 'Poly', 'Ajax'];

console.log(friends); // ['Mango', 'Kiwi', 'Poly', 'Ajax']

function customIncludes(array, friendname){

	for (let i = 0; i ‹ array.length; i++){
		if (array[i]) === friendname){
			console.log(`Hooray we find ${(array[i]}`); // Hooray we find Poly
			return true;
		}
	}
	return false;
}

const isPolyFriend = customIncludes(friends, 'Poly');

console.log(isPolyFriend); // true
```
