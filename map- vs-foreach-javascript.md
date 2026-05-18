Here is the comparison between `map` and `forEach` formatted as a Markdown document.

# JavaScript: `map()` vs `forEach()`

In JavaScript, `map()` and `forEach()` are two of the most frequently used methods for iterating over arrays. While they share a similar syntax, they serve different purposes and behave differently regarding return values and data manipulation.

---

## 1. Quick Comparison Table

| Feature | `map()` | `forEach()` |
| :--- | :--- | :--- |
| **Return Value** | Returns a **new array** containing the results of the callback. | Returns **`undefined`**. |
| **Original Array** | Does not mutate the original array. | Does not mutate the original array. |
| **Chaining** | **Yes**. You can chain `.filter()`, `.reduce()`, etc. | **No**. Since it returns `undefined`, you cannot chain. |
| **Purpose** | **Transformation**: Changing data into a new format. | **Side Effects**: Logging, saving to DB, or DOM manipulation. |

---

## 2. Visual Representation



## 3. The `map()` Method
The `map()` method creates a **new array** populated with the results of calling a provided function on every element in the calling array.

### Use Case: Transforming Data
Use `map` when you want to "map" one set of values to another.

```javascript
const prices = [10, 20, 30];
const taxRate = 1.1;

// Creating a new array with tax applied
const pricesWithTax = prices.map(price => price * taxRate);

console.log(pricesWithTax); // [11, 22, 33]
console.log(prices);        // [10, 20, 30] (Original is safe)
```

---

## 4. The `forEach()` Method
The `forEach()` method executes a provided function once for each array element. It is essentially a more readable version of a standard `for` loop.

### Use Case: Side Effects
Use `forEach` when you need to perform an action *for* every item but don't need to return a new array.

```javascript
const items = ['apple', 'banana', 'cherry'];

items.forEach((item, index) => {
  console.log(`${index + 1}: ${item}`);
});

// Output:
// 1: apple
// 2: banana
// 3: cherry
```

---

## 5. Key Differences to Remember

### Chaining
Because `map()` returns an array, you can keep adding methods to it:
```javascript
const numbers = [1, 2, 3, 4];
const result = numbers
  .map(n => n * 10)
  .filter(n => n > 25); 

console.log(result); // [30, 40]
```

### Performance & Memory
- **`map()`** allocates memory for a new array. If you don't intend to use the returned array, using `map()` is inefficient.
- **`forEach()`** is often slightly more performant for simple iterations where no new data structure is needed.

---

## Summary: Which should you use?
- Use **`map()`** if you are transforming data (e.g., converting an array of objects into an array of strings).
- Use **`forEach()`** if you are performing an action (e.g., updating a database or logging to the console).
- Use **`for...of`** if you need to use `break` or `continue` (which neither `map` nor `forEach` support).
