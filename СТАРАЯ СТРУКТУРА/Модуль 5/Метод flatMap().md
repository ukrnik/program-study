Метод `flatMap(callback)` аналогичный [[Метод .map()]], но используют эго чтобы сгладить многомерный [[Масиви]] 

```js
array.flatMap((element, index, array) => {
  // Тіло колбек-функції
});
```

Метод flatMap вызывает колбек-функцию для каждого элемента исходного массива, а результат работы записывает в новый массив. Отличие от map() заключается в том, что новый массив «разглаживается» на глубину, равную единице (одна вложенность). Этот разглаженный (плоский) массив является результатом работы flatMap().

```js
const students = [
  { name: "Mango", courses: ["mathematics", "physics"] },
  { name: "Poly", courses: ["science", "mathematics"] },
  { name: "Kiwi", courses: ["physics", "biology"] },
];

const mappedCourses = students.map(student => student.courses);
console.log(mappedCourses) // [["mathematics", "physics"], ["science", "mathematics"], ["physics", "biology"]]

const flattenedCourses = students.flatMap(student => student.courses);
console.log(flattenedCourses) // ["mathematics", "physics", "science", "mathematics", "physics", "biology"];

```
