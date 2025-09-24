
# Find nth Fibonacci Number Using Recursion

The **nth Fibonacci number** is defined as:  
\[
F(n) = F(n-1) + F(n-2), \quad F(1) = 1, F(2) = 1
\]

---

## Examples

| Input | Output | Explanation                     |
|-------|--------|---------------------------------|
| 1     | 1      | First Fibonacci number is 1    |
| 20    | 6765   | 20th Fibonacci number is 6765 |

**Constraints:** 1 ≤ n ≤ 20

---

## Recursive Approach

- **Base Cases:**  
  - F(1) = 1  
  - F(2) = 1  
- **Recursive Case:**  
  - F(n) = F(n-1) + F(n-2)  

---

### Implementation

```js
class Solution {
    fibonacci(n) {
        if (n === 1) return 1;  // Base case
        if (n === 2) return 1;  // Base case
        return this.fibonacci(n - 1) + this.fibonacci(n - 2); // Recursive call
    }
}

// Example usage
const sol = new Solution();
console.log(sol.fibonacci(1));  // Output: 1
console.log(sol.fibonacci(20)); // Output: 6765
````

---

## Complexity

* **Time Complexity:** O(2^n)

  * Each call branches into two recursive calls.
* **Auxiliary Space:** O(n)

  * Recursion stack depth is at most n.

---

**Note:**

* For larger `n`, recursion is inefficient due to repeated calculations.
* Can optimize using **memoization** or **iterative approach**.

