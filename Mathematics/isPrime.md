# Check if a Number is Prime

## Problem Statement

Given a number `n`, check if it is a **prime number** or not.

> A prime number is a natural number greater than 1 that is only divisible by 1 and itself.

---

## Examples

**Input:**  
`n = 5`  
**Output:**  
`true`  
**Explanation:** 5 is only divisible by 1 and 5. So, it is prime.

**Input:**  
`n = 4`  
**Output:**  
`false`  
**Explanation:** 4 is divisible by 2, hence not a prime number.

---

## Constraints

- 1 ≤ n ≤ 10⁹

---

## Solution in JavaScript

```javascript
/**
 * @param {number} n
 * @returns {boolean}
 */
class Solution {
    isPrime(n) {
        // Numbers less than or equal to 1 are not prime
        if (n <= 1) return false;

        // 2 is the only even prime number
        if (n === 2) return true;

        // Check for divisibility from 2 to √n
        for (let i = 2; i <= Math.sqrt(n); i++)
