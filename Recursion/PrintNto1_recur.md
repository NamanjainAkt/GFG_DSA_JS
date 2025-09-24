
# Print Numbers from N to 1

Given a number `N`, the task is to print numbers from `N` down to `1`.

---

## Examples

**Input:** N = 10  
**Output:** 10 9 8 7 6 5 4 3 2 1  

**Input:** N = 7  
**Output:** 7 6 5 4 3 2 1  

---

## Approach 1: Iterative

Use a simple loop from N down to 1.

```js
function printReverseOrder(N) {
  for (let i = N; i > 0; i--) {
    console.log(i);
  }
}

// Driver code
(function main() {
  const N = 5;
  printReverseOrder(N);
})();
````

**Output:**

```
5 4 3 2 1
```

* **Time Complexity:** O(N)
* **Auxiliary Space:** O(1)

---

## Approach 2: Recursive

Break the problem into smaller subproblems using recursion.

1. Check the base case `N <= 0`.
2. If base case is satisfied, return.
3. Otherwise, print `N` and call the function recursively with `N-1`.

```js
function printReverseOrder(N) {
  if (N <= 0) return;

  console.log(N);           // print current number
  printReverseOrder(N - 1); // recursive call
}

// Driver code
(function main() {
  const N = 5;
  printReverseOrder(N);
})();
```

**Output:**

```
5 4 3 2 1
```

* **Time Complexity:** O(N)
* **Auxiliary Space:** O(N) (due to recursive call stack)

---

## Note

1. Iteration is more efficient than recursion for this problem because recursion adds **call stack overhead**.
2. Recursion is mainly used here to **practice recursion**, understand **base cases**, and see how the **call stack** works.
