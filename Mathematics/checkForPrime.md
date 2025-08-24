# Prime Number Detection

## Overview
A prime number is a natural number greater than 1 that has exactly two distinct positive divisors: 1 and itself.

### Key Properties
- 2 is the only even prime number
- 1 is neither prime nor composite
- Any prime > 3 can be expressed as 6k ± 1
- Examples: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29

## Implementations

### 1. Naive Method
```javascript
function isPrimeNaive(n) {
  if (n === 1) return false;
  for (let i = 2; i < n; i++) {
    if (n % i === 0) return false;
  }
  return true;
}
```
- Complexity: Time O(n), Space O(1)

### 2. Optimized (Square Root Method) - Recommended

```javascript
function isPrimeOptimized(n) {
  if (n <= 1) return false;
  if (n <= 3) return true;
  for (let i = 2; i * i <= n; i++) {
    if (n % i === 0) return false;
  }
  return true;
}
```
- Complexity: Time O(√n), Space O(1)

### 3. Most Efficient (6k ± 1 Form)
```javascript
function isPrimeMostEfficient(n) {
  if (n <= 1) return false;
  if (n <= 3) return true;
  if (n % 2 === 0 || n % 3 === 0) return false;
  for (let i = 5; i * i <= n; i += 6) {
    if (n % i === 0 || n % (i + 2) === 0) return false;
  }
  return true;
}
```
- Complexity: Time O(√n), Space O(1)

# How It Works
### Square Root Method: Only check divisors up to √n since divisors come in pairs

### 6k ± 1 Method: Skip numbers divisible by 2 or 3, only check numbers of form 6k ± 1

### Recommendation
## Use the Square Root Method for most cases:

- Simple to implement

- Efficient enough for most applications

- Time complexity O(√n)

- Use the 6k ± 1 Method for performance-critical tasks:

- Fastest implementation

- Best for very large numbers

- Same time complexity with better constant factors