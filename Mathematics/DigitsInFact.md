# Number of Digits in Factorial

## Problem Statement

Given an integer `n`, find the number of digits in the value of `n!` (n factorial).

---

## Examples

**Input:**  
`n = 5`  
**Output:**  
`3`  
**Explanation:**  
5! = 120 → Number of digits = 3 (digits are 1, 2, 0)

**Input:**  
`n = 120`  
**Output:**  
`199`  
**Explanation:**  
120! has 199 digits

---

## Constraints

- 1 ≤ n ≤ 10⁵

---

## Solution in JavaScript

```javascript
/**
 * @param {number} n
 * @returns {number}
 */
class Solution {
    digitsInFactorial(n) {
        // Edge case: factorial of 0 or 1 has only 1 digit
        if (n === 0 || n === 1) return 1;

        let digits = 0;

        // Use logarithmic summation to calculate number of digits in n!
        for (let i = 2; i <= n; i++) {
            digits += Math.log10(i);
        }

        // Number of digits = floor(log10(n!)) + 1
        return Math.floor(digits) + 1;
    }
}
