# Find Roots of a Quadratic Equation

## Problem Statement

Given a quadratic equation of the form **ax² + bx + c = 0**, you have to find its roots.

- If the equation has real roots, return the **floor value** of each root in **decreasing order**.
- If the roots are imaginary, return `-1`. The driver code will print `Imaginary`.

---

## Examples

**Input:**  
`a = 1, b = -2, c = 1`  
**Output:**  
`1 1`  
**Explanation:** Roots of the equation x² - 2x + 1 are 1 and 1.

**Input:**  
`a = 1, b = -7, c = 12`  
**Output:**  
`4 3`  
**Explanation:** Roots of the equation x² - 7x + 12 are 4 and 3.

---

## Constraints

- -10³ ≤ a, b, c ≤ 10³

---

## Solution in JavaScript

```javascript
/**
 * @param {number} a
 * @param {number} b
 * @param {number} c
 * @returns {number[]} (array)
 */
class Solution {
    quadraticRoots(a, b, c) {
        // Calculate discriminant
        let D = b * b - 4 * a * c;
        let roots = [];

        // Check if roots are imaginary
        if (D < 0) return [-1];

        // Calculate both roots
        let sqrtD = Math.sqrt(D);
        let x1 = Math.floor((-b + sqrtD) / (2 * a));
        let x2 = Math.floor((-b - sqrtD) / (2 * a));

        // Return roots in decreasing order
        return x1 >= x2 ? [x1, x2] : [x2, x1];
    }
}
