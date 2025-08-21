# Convert Celsius to Fahrenheit

## Problem Statement

Given a temperature in Celsius `C`, you need to convert the given temperature into Fahrenheit.

### Examples

**Input:**  
`C = 32`  
**Output:**  
`89.6`  
**Explanation:** Using the conversion formula of Celsius to Fahrenheit,  
F = (C × 9/5) + 32  
=> F = (32 × 9/5) + 32 = 89.6

**Input:**  
`C = 50`  
**Output:**  
`122`  
**Explanation:**  
F = (50 × 9/5) + 32 = 122

### Constraints

- 1 ≤ C ≤ 10⁴

---

## Solution in JavaScript

```javascript
/**
 * @param {number} C
 * @returns {number}
 */
class Solution {
    cToF(C) {
        // Convert Celsius to Fahrenheit using the formula: F = (C × 9/5) + 32
        return (C * 9 / 5) + 32;
    }
}
