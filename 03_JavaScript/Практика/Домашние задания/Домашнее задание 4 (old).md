## Task 1

```js
function isEnoughCapacity(products, containerSize) {
	let totalSizeArray = [];
	let result = 0;

	for (const key in products) {
		totalSizeArray.push(products[key]);
	}

	for (let name of totalSizeArray) {
		result += name;
	}

	if (result <= containerSize) {
		return true;
	}
	return false;
}

console.log(isEnoughCapacity({ apples: 2, grapes: 3, carrots: 1 }, 8)); // true
console.log(isEnoughCapacity({ apples: 4, grapes: 6, lime: 16 }, 12)); // false
console.log(isEnoughCapacity({ apples: 1, lime: 5, tomatoes: 3 }, 14)); // true
console.log(isEnoughCapacity({ apples: 18, potatoes: 5, oranges: 2 }, 7)); // false
```
## Task 2

```js
function calcAverageCalories(params) {
	let totalCallories = 0;
	for (const key of params) {
		totalCallories += key.calories;
	}

	let result = totalCallories / params.length;

	if (isNaN(result)) {
		return 0;
	}
	return result;
}

console.log(calcAverageCalories([
{ day: "monday", calories: 3010 },
{ day: "tuesday", calories: 3200 },
{ day: "wednesday", calories: 3120 },
{ day: "thursday", calories: 2900 },
{ day: "friday", calories: 3450 },
{ day: "saturday", calories: 3280 },
{ day: "sunday", calories: 3300 }
])); // 3180

console.log(calcAverageCalories([
{ day: "monday", calories: 2040 },
{ day: "tuesday", calories: 2270 },
{ day: "wednesday", calories: 2420 },
{ day: "thursday", calories: 1900 },
{ day: "friday", calories: 2370 },
{ day: "saturday", calories: 2280 },
{ day: "sunday", calories: 2610 }
])); // 2270

console.log(calcAverageCalories([])); // 0
```
## Task 3

```js
const profile = {
	username: "Jacob",
	playTime: 300,

	changeUsername(newName) {
		profile.username = newName;
	},

	updatePlayTime(hours) {
		profile.playTime += hours;
	},

	getInfo() {
		return `${this.username} has ${this.playTime} active hours!`
	}
};

console.log(profile.getInfo()); // "Jacob has 300 active hours!"
profile.changeUsername("Marco");

console.log(profile.getInfo()); // "Marco has 300 active hours!"
profile.updatePlayTime(20);

console.log(profile.getInfo()); // "Marco has 320 active hours!"
```