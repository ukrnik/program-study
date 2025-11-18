Перебирает по этапно каждый элемент масива не изменяя оригинал и выполняет манипуляции в [[Callback функции]] 

```js
array.map((element, index, array) => {
  // Тіло колбек-функції
});
```

Метод использую чтобы изменить каждый элемент оригинального [[Масиви]]

```js
const planets = ["Earth", "Mars", "Venus", "Jupiter"];

const planetsInUpperCase = planets.map(planet => planet.toUpperCase());
console.log(planetsInUpperCase); // ["EARTH", "MARS", "VENUS", "JUPITER"]

const planetsInLowerCase = planets.map(planet => planet.toLowerCase());
console.log(planetsInLowerCase); // ["earth", "mars", "venus", "jupiter"]

// Оригінальний масив не змінився
console.log(planets); // ["Earth", "Mars", "Venus", "Jupiter"]
```

