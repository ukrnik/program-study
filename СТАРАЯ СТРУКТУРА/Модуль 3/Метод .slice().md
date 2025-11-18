.slice() делает копию масива и может копировать определённые участки масива

В скобки () мы можем вставить начальный индекс с которого будет срез .slice(start) или начальный и конечный индекс .slice(start, end)

```js
const courses = ['HTML', 'CSS', 'JavaScript', 'React', 'PostgreSQL'];

const coursesSlice = courses.slice(2, 4);

console.log(coursesSlice); // ['JavaScript', 'React',]
```

Если мы ничего не передаём в скобки то создается полная независимая копия масива на которой можно делать отдельные действия без последствий для первого копируемого масива

```js
const courses = ['HTML', 'CSS', 'JavaScript', 'React', 'PostgreSQL'];

const coursesSlice = courses.slice();

coursesSlice[0] = 'Rex'

console.log(courses); // ['HTML', 'CSS', 'JavaScript', 'React', 'PostgreSQL']
console.log(coursesSlice); // ['Rex', 'CSS', 'JavaScript', 'React', 'PostgreSQL']
```

Если мы передаем только одно значение number в split() то будет делаться копия со срезом от начального индекса который мы передали и до последнего 

```js
const courses = ['HTML', 'CSS', 'JavaScript', 'React', 'PostgreSQL'];

const coursesSlice = courses.slice(2);

console.log(courses); // ['JavaScript', 'React', 'PostgreSQL']
```
