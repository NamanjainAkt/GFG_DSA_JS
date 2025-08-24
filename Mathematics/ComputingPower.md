# Power Calculation (xⁿ)

## Overview
Given two integers `x` and `n`, compute `x` raised to the power `n` (xⁿ).

## Examples
- `x = 2, n = 3` → 8
- `x = 7, n = 2` → 49

## Implementations

### 1. Naive Iterative Approach
```javascript
function power(x, n) {
  let result = 1;
  for (let i = 0; i < n; i++) {
    result *= x;
  }
  return result;
}
```
- Complexity: Time O(n), Space O(1)

### 2. Optimized Divide and Conquer (Recursive) - Recommended
```javascript
function power(x, n) {
  if (n === 0) return 1;
  
  let temp = power(x, Math.floor(n / 2));
  
  if (n % 2 === 0) {
    return temp * temp;
  } else {
    return x * temp * temp;
  }
}
```
- Complexity: Time O(log n), Space O(log n)

### 3. Iterative Optimized Approach (Binary Exponentiation)
```javascript
function power(x, n) {
  let result = 1;
  
  while (n > 0) {
    // If n is odd, multiply x with result
    if (n % 2 === 1) {
      result *= x;
    }
    
    // Square x and halve n
    x *= x;
    n = Math.floor(n / 2);
  }
  
  return result;
}
```
- Complexity: Time O(log n), Space O(1)

### How It Works
#### The optimized approach uses binary exponentiation:

- Divide and conquer: xⁿ = (xⁿ/²)²

- Handle odd exponents: xⁿ = x × (x⁽ⁿ⁻¹⁾/²)²

- Iterative version: Uses bit manipulation to avoid recursion

- Key Formulas
If n is even: xⁿ = (xⁿ/²) × (xⁿ/²)

- If n is odd: xⁿ = x × (x⁽ⁿ⁻¹⁾/²) × (x⁽ⁿ⁻¹⁾/²)

#### Recommendation
- Use the Iterative Optimized Approach:

- Best time complexity: O(log n)

- Constant space: O(1)

- No recursion stack overhead

- Efficient for large exponents