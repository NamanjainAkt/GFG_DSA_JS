# Greatest Common Divisor (GCD)

## Overview
The Greatest Common Divisor (GCD) of two integers `a` and `b` is the largest positive integer that divides both numbers without leaving a remainder.

## Examples
- `a=4, b=6` → GCD is 2
- `a=100, b=20` → GCD is 20
- `a=7, b=13` → GCD is 1

## Implementations

### 1. Naive Method
```javascript
function naiveGCD(a, b) {
  let res = Math.min(a, b);
  while (res > 0) {
    if (a % res === 0 && b % res === 0) return res;
    res--;
  }
  return res;
}
```

Complexity: Time O(min(a,b)), Space O(1)

2. Euclidean Algorithm (Recursive)

```javascript
function euclideanGCD(a, b) {
  if (b === 0) return a;
  return euclideanGCD(b, a % b);
}
```

Complexity: Time O(log(min(a,b))), Space O(log(min(a,b)))

3. Euclidean Algorithm (Iterative) - Recommended

```javascript
function iterativeGCD(a, b) {
  while (b !== 0) {
    [a, b] = [b, a % b];
  }
  return a;
}
```

Complexity: Time O(log(min(a,b))), Space O(1)

Recommendation
Use the iterative Euclidean algorithm for best performance:

Fastest time complexity: O(log(min(a,b)))

Constant space: O(1)

No recursion stack overflow risk

Simple implementation
