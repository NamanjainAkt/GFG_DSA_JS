
# Power of Number Raised to Its Reverse

Given a number `n`, calculate **n raised to the power of its reverse**.

---

## Examples

| Input | Output | Explanation |
|-------|--------|-------------|
| 2     | 4      | Reverse of 2 is 2 → 2² = 4 |
| 10    | 10     | Reverse of 10 is 1 → 10¹ = 10 |

**Constraints:** 1 ≤ n ≤ 10

---

## Approach

1. Convert the number `n` to a string.  
2. Reverse the string and convert it back to a number.  
3. Compute `n` raised to the power of the reversed number.  
4. Return the result.

---

### Implementation

```js
class Solution {
    ReverseExponentiation(n) {
        // Convert number to string and reverse
        const reversedNum = parseInt(n.toString().split("").reverse().join(""));
        // Compute power
        return Math.pow(n, reversedNum);
    }
}

// Example usage
const sol = new Solution();
console.log(sol.ReverseExponentiation(2));  // Output: 4
console.log(sol.ReverseExponentiation(10)); // Output: 10
````

---

## Complexity

* **Time Complexity:** O(d), where `d` is the number of digits in `n` (for reversing the number)
* **Auxiliary Space:** O(d) (for string conversion)

**Note:**

* Leading zeros in the reversed number are discarded automatically when converting back to a number.
