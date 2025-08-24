# Divisors of a Natural Number

## Overview
Given a natural number `n`, find all distinct divisors (factors) that divide `n` without leaving a remainder.

## Examples
- `n = 10` → 1, 2, 5, 10
- `n = 100` → 1, 2, 4, 5, 10, 20, 25, 50, 100  
- `n = 125` → 1, 5, 25, 125

## Implementations

### 1. Naive Solution
```javascript
function printDivisors(n) {
  for (let i = 1; i <= n; i++) {
    if (n % i === 0) {
      console.log(i);
    }
  }
}
Complexity: Time O(n), Space O(1)

2. Efficient Solution (Unsorted)
javascript
function printDivisors(n) {
  for (let i = 1; i <= Math.sqrt(n); i++) {
    if (n % i === 0) {
      console.log(i);
      if (i !== n / i) {
        console.log(n / i);
      }
    }
  }
}
Complexity: Time O(√n), Space O(1)

3. Efficient Solution (Sorted) - Recommended
javascript
function printDivisors(n) {
  let i = 1;
  // Print divisors from 1 to √n
  for (i = 1; i * i < n; i++) {
    if (n % i === 0) {
      console.log(i);
    }
  }
  
  // Print divisors from √n to n
  for (; i >= 1; i--) {
    if (n % i === 0) {
      console.log(n / i);
    }
  }
}
```
- Complexity: Time O(√n), Space O(1)

## How It Works
### Divisors come in pairs (i, n/i). For example:

- 100: (1,100), (2,50), (4,25), (5,20), (10,10)

- Only need to check up to √n to find all divisor pairs

- The sorted solution collects smaller divisors first, then larger ones

### Recommendation
#### Use the Efficient Sorted Solution:

- Optimal time complexity: O(√n)

- Returns divisors in ascending order

- Handles perfect squares correctly (e.g., 10×10)

- Constant space complexity