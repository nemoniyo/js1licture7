"# js1licture7" 

# JavaScript Callbacks

## Что такое Callback в JavaScript?

Callback-функция в JavaScript — это функция, которая передается в другую функцию в качестве аргумента и вызывается позже, когда другая функция завершает выполнение.

### Пример:

```javascript
function greet(name, callback) {
    console.log("Привет, " + name + "!");
    callback(); // вызываем переданную функцию
}

function sayGoodbye() {
    console.log("Пока, до скорой встречи!");
}

greet("Алина", sayGoodbye);
// Вывод:
// Привет, Алина!
// Пока, до скорой встречи!
```

---

## Callback-функции для массивов с примерами

### 1. `forEach()`

Метод `forEach()` выполняет указанную функцию для каждого элемента массива. **Не возвращает новый массив.**

```javascript
const numbers = [1, 2, 3];
numbers.forEach((num, index) => {
    console.log(`Индекс: ${index}, Значение: ${num}`);
});
// Вывод:
// Индекс: 0, Значение: 1
// Индекс: 1, Значение: 2
// Индекс: 2, Значение: 3
```

---

### 2. `map()`

Метод `map()` создает новый массив, применяя callback ко всем элементам оригинального массива.

```javascript
const numbers = [1, 2, 3];
const squares = numbers.map(num => num * num);
console.log(squares); // [1, 4, 9]
```

---

### 3. `filter()`

Метод `filter()` создает новый массив, содержащий только элементы, которые соответствуют условию в callback.

```javascript
const numbers = [1, 2, 3, 4];
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // [2, 4]
```

---

### 4. `find()`

Метод `find()` возвращает первый элемент, который удовлетворяет условию в callback. Если ничего не найдено, возвращает `undefined`.

```javascript
const numbers = [1, 2, 3, 4];
const firstEven = numbers.find(num => num % 2 === 0);
console.log(firstEven); // 2
```

---

### 5. `toSorted()` (ES2023)

Метод `toSorted()` создает новый массив с элементами, отсортированными на основе callback.

```javascript
const numbers = [3, 1, 4, 2];
const sorted = numbers.toSorted((a, b) => a - b);
console.log(sorted); // [1, 2, 3, 4]
```

---

### 6. `reduce()`

Метод `reduce()` применяет callback к каждому элементу массива, возвращая одно итоговое значение.

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // 10
```

---

### 7. `some()`

Метод `some()` возвращает `true`, если хотя бы один элемент массива соответствует условию в callback.

```javascript
const numbers = [1, 2, 3, 4];
const hasEven = numbers.some(num => num % 2 === 0);
console.log(hasEven); // true
```

---

### 8. `every()`

Метод `every()` возвращает `true`, если все элементы массива соответствуют условию в callback.

```javascript
const numbers = [2, 4, 6];
const allEven = numbers.every(num => num % 2 === 0);
console.log(allEven); // true
```

