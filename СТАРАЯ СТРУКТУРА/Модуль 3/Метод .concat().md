.concat помогает соединить два и более масива в один, в последствии будет создан отдельный масив с елементами двух и более масивов

В скобки () мы передаем масиви которые мы хотим обьеденить. Порядок сохраняется

```js
const courses = ['HTML', 'CSS', 'JavaScript'];
const coursesNew = ['React', 'PostgreSQL']
const coursesNewSecond = [0, 2, 55]

const coursesUpdate = courses.concat(coursesNew, coursesNewSecond);
console.log(coursesUpdate); // ['HTML', 'CSS', 'JavaScript', 'React', 'PostgreSQL', 0, 2, 55]
```