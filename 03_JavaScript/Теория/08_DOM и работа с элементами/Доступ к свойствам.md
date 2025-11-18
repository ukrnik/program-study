После того как [[DOM]]-дерево было построено то некоторые свойства HTML тегов стают подвластными для переопределения.

Используя методы:
- [[element.querySelectorAll]]
- [[element.querySelector]]

Если в HTML есть тег ссылка

```html
<a class="link" href="https://goit.global">GoIT</a>;
```

Мы можем прочитать значения атрибута из ссылки. Для этого нам нужно получить ссылку на элемент и обратится к значениям

```js
const link = document.querySelector(".link");
console.log(link.href); // "https://goit.global"
```

Значения атрибутов можно изменять, переопределив им новое значение прямо из JavaScript кода, и при выполнении скрипта значение в HTML, то есть в DOM-дереве, изменится.

```js
const link = document.querySelector(".link");
console.log(link.href); // "https://goit.global"
link.href = "https://neo.goit.global";
console.log(link.href); // "https://neo.goit.global"
```

## Популярный поиск за [[CSS-Selector|CSS-селектором]]:

#### 1) Элемент (type selector): выбирает все элементы заданного типа.

```html
<li>home</li>
```

#### 2) Класс (class selector): выбирает все элементы с указанным классом.

```html
<li class="menu-item">home</li>
```

#### 3) ID (ID selector): выбирает элемент с указанным уникальным ID.


```html
<li id="menu">home</li>
```

---