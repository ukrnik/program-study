# Методы Date (set) — установка даты и времени

Методы **`set`** позволяют изменять части даты и времени в объекте `Date`.

> [!warning] Важно
> При выходе за допустимые значения (date.setDate(32)) JavaScript автоматически корректирует дату (переносит на следующий месяц).
> Месяцы считаются с **0** (январь) до **11** (декабрь).

---
## Таблица методов

| Метод                 | Описание                                       | Пример |
| --------------------- | ---------------------------------------------- | ------- |
| `.setFullYear(year)`  | Устанавливает год                              | `date.setFullYear(2024)` |
| `.setMonth(month)`    | Устанавливает месяц (0–11)                     | `date.setMonth(0)` (январь) |
| `.setDate(day)`       | Устанавливает число месяца (1–31)              | `date.setDate(25)` |
| `.setHours(hours)`    | Устанавливает часы (0–23)                      | `date.setHours(15)` |
| `.setMinutes(min)`    | Устанавливает минуты (0–59)                    | `date.setMinutes(45)` |
| `.setSeconds(sec)`    | Устанавливает секунды (0–59)                   | `date.setSeconds(30)` |
| `.setMilliseconds(ms)`| Устанавливает миллисекунды (0–999)             | `date.setMilliseconds(500)` |
| `.setTime(ms)`        | Устанавливает дату по метке времени (мс)       | `date.setTime(1755250200000)` |

---
## Примеры использования

```js
const date = new Date(2025, 7, 15, 10, 30, 0);

date.setFullYear(2030);
console.log(date); // Thu Aug 15 2030 10:30:00

date.setMonth(0);  // Январь (месяцы начинаются с 0)
console.log(date); // Tue Jan 15 2030 10:30:00

date.setDate(1); 
console.log(date); // Tue Jan 01 2030 10:30:00

date.setHours(23);
date.setMinutes(59);
console.log(date); // Tue Jan 01 2030 23:59:00

date.setSeconds(30);
date.setMilliseconds(500);
console.log(date); // Tue Jan 01 2030 23:59:30.500

// Установка через timestamp
date.setTime(1700000000000);
console.log(date); // Sun Nov 14 2023 22:13:20
```

---