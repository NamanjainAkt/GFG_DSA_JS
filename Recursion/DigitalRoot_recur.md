
# Digital Root of a Number Using Recursion

The **digital root** of a number is the recursive sum of its digits until a single-digit number is obtained.

---

## Examples

| Input    | Output | Explanation |
|----------|--------|-------------|
| 1        | 1      | Digital root of 1 is 1 |
| 99999    | 9      | 9+9+9+9+9 = 45 → 4+5 = 9 |

**Constraints:** 1 ≤ n ≤ 10^7

---

## Recursive Approach

**Steps:**

1. **Base Case:**  
   - If `n <= 9`, return `n` (single-digit).  
2. **Recursive Case:**  
   - Compute sum of digits of `n`.  
   - Recursively call the function on this sum.

---

### Implementation

```js
class Solution {
    digitalRoot(n) {
        if (n <= 9) return n; // Base case

        let sum = 0;
        while (n > 0) {
            sum += n % 10;          // Add last digit
            n = Math.floor(n / 10); // Remove last digit
        }

        return this.digitalRoot(sum); // Recursive call
    }
}

// Example usage
const sol = new Solution();
console.log(sol.digitalRoot(1));      // Output: 1
console.log(sol.digitalRoot(99999));  // Output: 9
````

---

## How It Works

* For `n = 99999`:

```
99999 → 9+9+9+9+9 = 45
45 → 4+5 = 9
Digital root = 9
```

---

## Complexity

* **Time Complexity:** O(log n)

  * Each recursion reduces the number of digits.
* **Auxiliary Space:** O(log n) (recursion stack)

**Note:**

* Iterative approach can also be used to avoid recursion stack overhead.
* For extremely large `n`, digital root can also be computed in O(1) using the formula:

$$
\text{digitalRoot}(n) = 1 + ((n - 1) \% 9)
$$


