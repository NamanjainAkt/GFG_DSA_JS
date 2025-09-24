

## 📌 Arrays – Overview

### ✅ What is an Array?

* An **array** is a collection of items of the same data type stored in **contiguous memory locations**.
* Each item is accessed using an **index** (starting from `0`).
* Example:

  ```js
  let arr = [10, 20, 30, 40];
  ```

---

### ✅ Why Do We Use Arrays?

* To store **multiple related items** in a single variable.
* Efficient for large datasets (instead of declaring many variables like `v1, v2, v3...`).
* Common in all programming languages: **C, C++, Java, JavaScript, Python**.
* Used in real-life apps like storing a **friends list, leaderboard scores, student marks, etc.**

---

### ✅ Basic Terminologies

1. **Array Index** → Position of element (`0`-based).
2. **Array Element** → Actual stored value.
3. **Array Length** → Number of elements.

Example:

```js
let arr = [10, 20, 30];
Index →   0   1   2
```

---

### ✅ Representation

* **Static (C, C++)**

  ```c
  int arr[10]; // Fixed size
  ```
* **Dynamic (JavaScript, Python, Java)**

  ```js
  let arr = [10, 20, 30]; // Flexible size
  ```

---

### ✅ Dynamic Nature (JavaScript Arrays)

* JavaScript arrays **grow/shrink automatically**.
* Example:

  ```js
  let arr = [10, 20];
  arr.push(30);    // [10, 20, 30]
  arr.unshift(5);  // [5, 10, 20, 30]
  ```

---

### ✅ Insertion & Deletion (JavaScript)

| Operation             | Method      | Description               |
| --------------------- | ----------- | ------------------------- |
| Insert at end         | `push()`    | Adds element at end       |
| Remove from end       | `pop()`     | Removes last element      |
| Insert at beginning   | `unshift()` | Adds element at beginning |
| Remove from beginning | `shift()`   | Removes first element     |

---

### ✅ Why Arrays are Needed?

* Without arrays → we need multiple variables for data (`marks1, marks2, …`).
* With arrays → one variable can store **many items**, easy to **access, loop, modify**.
* Arrays are the **foundation** for other data structures: **Linked List, Stack, Queue, Trees, Graphs**.

---

📖 **In short:**
Arrays = **collection of items in order, indexed, efficient for storage & manipulation, foundation for advanced DS**.

---
