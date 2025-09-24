
# Sum of First n Natural Numbers Using Recursion

Given a number `n`, find the sum of the first `n` natural numbers using recursion.

---

## Examples

**Input:** 3  
**Output:** 6  
**Explanation:** 1 + 2 + 3 = 6  

**Input:** 5  
**Output:** 15  
**Explanation:** 1 + 2 + 3 + 4 + 5 = 15  

---

## Approach

- **Recursive formula:**  
\[
\text{sum(n)} = n + \text{sum(n-1)}
\]
- **Base Case:** If n = 1, return 1.

---

## Decreasing Recursion (n → 1)

```js
function recur_sum(n) {
  if (n === 1) return 1;             // Base case
  let answer = n + recur_sum(n - 1); // Recursive call
  return answer;
}

console.log(recur_sum(5)); // Output: 15
````

**How it works for n = 3:**

```
recur_sum(3) → 3 + recur_sum(2)
recur_sum(2) → 2 + recur_sum(1)
recur_sum(1) → 1 (base case)
Sum returns: 1 → 3 → 6
```

---

## Increasing Recursion (1 → n)

```js
function recur_sum(i, n) {
  if (i === n) return n;                  // Base case
  let answer = i + recur_sum(i + 1, n);  // Recursive call
  return answer;
}

console.log(recur_sum(1, 5)); // Output: 15
```

**How it works:**

* Starts from i = 1, adds numbers up to n.
* Base case returns n.
* Results sum back up through recursion.

---

## Complexity

* **Time Complexity:** O(N)
* **Space Complexity:** O(N) (due to recursion stack)

---

## Note

* Iterative approach is usually better:

  * Constant auxiliary space O(1)
  * Same time complexity O(N)
* Recursion is useful for understanding **concepts** or **naturally recursive problems** like trees.
