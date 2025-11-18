.join() - сшивает масив из строк в string.

```js
const courses = ['HTML', 'CSS', 'JavaScript', 'React', 'PostgreSQL'];
const coursesDesc = courses.join(' ');
console.log(coursesDesc); // "HTML CSS JavaScript React PostgreSQL"
```

в скобки мы вставляем разделитель.

```js
const courses = ['HTML', 'CSS', 'JavaScript', 'React', 'PostgreSQL'];
const coursesDesc = courses.join(' * ');
console.log(coursesDesc); // "HTML * CSS * JavaScript * React * PostgreSQL"
```
