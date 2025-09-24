
# Calculate n Raised to the Power p Using Recursion

Given two numbers `n` and `p`, find **n^p** using recursion.

---

## Examples

| Input     | Output      | Explanation                        |
|-----------|------------|------------------------------------|
| n = 9, p = 9 | 387420489 | 9⁹ = 387420489                    |
| n = 2, p = 9 | 512       | 2⁹ = 512                           |

**Constraints:**  
- 1 ≤ n ≤ 10  
- 0 ≤ p ≤ 9  

---

## Recursive Approach

- **Base Case:**  
  - If `p == 0`, return 1 (n⁰ = 1)  
- **Recursive Case:**  
  - n^p = n × n^(p-1)  

---

### Implementation

```js
class Solution {
    RecursivePower(n, p) {
        if (p === 0) return 1;              // Base case
        return n * this.RecursivePower(n, p - 1); // Recursive call
    }
}

// Example usage
const sol = new Solution();
console.log(sol.RecursivePower(9, 9)); // Output: 387420489
console.log(sol.RecursivePower(2, 9)); // Output: 512
````

---

## Complexity

* **Time Complexity:** O(p)
* **Auxiliary Space:** O(p) (due to recursion stack)

**Note:**

* Iterative approach can reduce auxiliary space to O(1).
* For small constraints (p ≤ 9), recursion works efficiently.

