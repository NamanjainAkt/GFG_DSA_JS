# Factorial of a Number

## Problem Statement

Given a positive integer `n`, you have to find the **factorial** of `n`.

The factorial of a number `n` is defined as:

**n! = n × (n-1) × (n-2) × ... × 1**  
Note: `0! = 1` by definition.

---

## Examples

**Input:**  
`n = 4`  
**Output:**  
`24`  
**Explanation:** `4! = 4 × 3 × 2 × 1 = 24`

**Input:**  
`n = 11`  
**Output:**  
`39916800`  
**Explanation:** `11! = 11 × 10 × ... × 1 = 39916800`

---

## Constraints

- 0 ≤ n ≤ 11

---

## Solution in JavaScript

```javascript
/**
 * @param {number} n
 * @returns {number}
 */
class Solution {
    factorial(n) {
        // Initialize factorial result
        let fact = 1;
        
        // Loop from 2 to n to calculate factorial
        for (let i = 2; i <= n; i++) {
            fact *= i;
        }
        
        return fact;
    }
}
