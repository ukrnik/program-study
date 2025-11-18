## Task 1

```js
const getUserNames = (users) => {return users.map((user) => user.name)};
```
## Task 2

```js
const getUsersWithFriend = (users, friendName) => {return users.filter(user => user.friends.includes(friendName))};
```
## Task 3

```js
const sortByDescendingFriendCount = (users) => {return users.toSorted((a, b) => b.friends.length - a.friends.length)};
```
## Task 4

```js
const getTotalBalanceByGender = (users, gender) => {return users.filter(user => user.gender === gender).reduce((acc, user) => {return acc + user.balance}, 0);};
```
