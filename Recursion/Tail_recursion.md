
# Tail Recursion in JavaScript

Recursion occurs when a function calls itself. **Tail recursion** is a special type where the **recursive call is the last statement** executed in the function.

---

## Tail Recursive Example

Print numbers from N down to 1:

```js
function printN(N) {
  if (N === 0) return;
  console.log(N);
  printN(N - 1); // recursive call at the end
}

printN(5); // Output: 5 4 3 2 1
````

---

## Non-Tail Recursive Example

Print numbers from 1 to N:

```js
function print(n) {
  if (n == 0) return;
  print(n - 1);     // recursive call first
  console.log(n);   // runs after recursion → not tail recursive
}

print(5); // Output: 1 2 3 4 5
```

**Problem:** Stack frames accumulate, cannot be optimized.

---

## Why Tail Recursion is Better

* Optimized by **Tail Call Optimization (TCO)**.
* Current function stack frame can be **reused**, saving memory.
* Prevents **stack overflow** in deep recursion.

---

## Converting Non-Tail to Tail Recursion

Use an **accumulator** or extra parameter to carry current progress:

```js
function printTail(n, k) {
  if (k > n) return;
  console.log(k);
  printTail(n, k + 1); // tail recursive call
}

printTail(3, 1); // Output: 1 2 3
```

---

## Tail Recursion in Sorting Algorithms

| Algorithm  | Tail Recursive? | Notes                                        |
| ---------- | --------------- | -------------------------------------------- |
| Merge Sort | ❌ No            | Merging happens after recursion              |
| Quick Sort | ✅ Yes           | Recursive calls at the end; memory efficient |

---

## Tail Recursion in Tree Traversals

| Traversal  | Tail Recursive? | Notes                              |
| ---------- | --------------- | ---------------------------------- |
| Pre-order  | ✅ Yes           | Root printed first, recursion last |
| In-order   | ✅ Partially     | Right recursive call is tail       |
| Post-order | ❌ No            | Print happens after recursion      |

---

## Factorial Examples

### Non-Tail Recursive Factorial

```js
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1); // multiplication after recursion
}
```

* Uses more stack space.
* Not tail recursive.

### Tail Recursive Factorial (Using Accumulator)

```js
function factorialTR(n, acc = 1) {
  if (n === 0) return acc;
  return factorialTR(n - 1, acc * n); // recursive call last
}
```

* Accumulator carries running product.
* Optimized memory usage and performance.

---

## Key Takeaways

* Tail recursion allows **stack frame reuse** and **memory optimization**.
* Recursive call must be **the last statement** to qualify.
* Some algorithms (merge sort, post-order traversal) **cannot** be tail recursive.
* Use **accumulators** or **helper parameters** to convert recursion to tail recursion where possible.
* Important for **efficient recursive code**, especially in functional programming.
