
# Count Number of Digits in a Number

Given a number `n`, find the **count of digits** in `n`.

---

## Examples

| Input   | Output | Explanation                  |
|---------|--------|------------------------------|
| 1       | 1      | Number of digits in 1 is 1  |
| 99999   | 5      | Number of digits in 99999 is 5 |

**Constraints:** 1 ≤ n ≤ 10^9

---

## Approach

- Use **logarithm** to count digits:  
\[
\text{digits} = \lfloor \log_{10}(|n|) \rfloor + 1
\]  
- Handles all positive integers.  
- Special case: if n = 0, the number of digits is 1.

---

### Implementation

```js
class Solution {
    countDigits(n) {
        if (n === 0) return 1; // Special case
        return Math.floor(Math.log10(Math.abs(n))) + 1;
    }
}

// Example usage
const sol = new Solution();
console.log(sol.countDigits(1));      // Output: 1
console.log(sol.countDigits(99999));  // Output: 5
````

---

## Complexity

* **Time Complexity:** O(1)
* **Auxiliary Space:** O(1)

---

**Note:**

* This approach avoids loops and recursion.
* Works efficiently for large numbers within given constraints.
