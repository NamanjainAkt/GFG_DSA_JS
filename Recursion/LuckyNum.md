
# Check if a Number is Lucky Using Recursion

A **lucky number** is defined via a special elimination process:

1. Start with natural numbers: 1, 2, 3, 4, 5, 6, ...  
2. In the 1st step, remove every 2nd number.  
3. In the 2nd step, remove every 3rd remaining number.  
4. In the 3rd step, remove every 4th remaining number, and so on...  

A number `n` is **lucky** if it survives all steps.

---

## Examples

| Input | Output | Explanation |
|-------|--------|-------------|
| 5     | 0      | 5 is deleted in the 2nd iteration |
| 19    | 1      | 19 survives all iterations |

**Constraints:** 1 ≤ n ≤ 10^5

---

## Recursive Approach

**Idea:**

- Keep track of the current elimination step `k`.  
- **Base Case:** If `k >= n`, the number survives → return 1.  
- **Check Deletion:** If `n % (k+1) === 0`, it gets deleted → return 0.  
- **Update Position:** After eliminating every `(k+1)`th number, the new position of `n` is:  
\[
n = n - \left\lfloor \frac{n}{k+1} \right\rfloor
\]  
- Recurse for next step `k+1`.

---

### Implementation

```js
class Solution {
    isLucky(n, k = 1) {
        if (k >= n) return 1;                // Survived all steps
        if (n % (k + 1) === 0) return 0;     // Deleted in current step

        n = n - Math.floor(n / (k + 1));     // Update position after elimination
        return this.isLucky(n, k + 1);       // Recurse for next step
    }
}

// Example usage
const sol = new Solution();
console.log(sol.isLucky(5));   // Output: 0
console.log(sol.isLucky(19));  // Output: 1
````

---

## Complexity

* **Time Complexity:** O(n) in the worst case
* **Auxiliary Space:** O(n) due to recursion stack

**Note:**

* This recursive approach simulates the elimination process efficiently without storing the entire sequence.
* Can be converted to an iterative approach to reduce recursion stack usage.

