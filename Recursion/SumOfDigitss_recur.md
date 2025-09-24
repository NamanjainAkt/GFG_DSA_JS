
# Sum of Digits of a Number Using Recursion

Given a number `n`, find the **sum of its digits** recursively.

---

## Examples

| Input   | Output | Explanation                  |
|---------|--------|------------------------------|
| 1       | 1      | Sum of digits of 1 is 1      |
| 99999   | 45     | 9+9+9+9+9 = 45               |

**Constraints:** 1 ≤ n ≤ 10^7

---

## Recursive Approach

1. **Base Case:**  
   - If `n <= 9`, return `n`.  
2. **Recursive Case:**  
   - Last digit: `n % 10`  
   - Remaining number: `Math.floor(n / 10)`  
   - Sum = `last digit + sumOfDigits(remaining)`

---

### Implementation

```js
class Solution {
    sumOfDigits(n) {
        if (n <= 9) return n; // Base case

        const lastDigit = n % 10;
        const remaining = Math.floor(n / 10);

        return this.sumOfDigits(remaining) + lastDigit; // Recursive call
    }
}

// Example usage
const sol = new Solution();
console.log(sol.sumOfDigits(1));      // Output: 1
console.log(sol.sumOfDigits(99999));  // Output: 45
````

---

## Complexity

* **Time Complexity:** O(D), where D = number of digits in `n`
* **Auxiliary Space:** O(D) (recursion stack)

**Note:**

* Iterative approach using a loop can reduce auxiliary space to O(1).
* Recursion is useful for understanding the concept of breaking a problem into smaller subproblems.

