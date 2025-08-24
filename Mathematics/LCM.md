# Least Common Multiple (LCM)

## Overview
The Least Common Multiple (LCM) of two integers `a` and `b` is the smallest positive integer that is divisible by both numbers.

## Examples
- `LCM(4, 6) = 12`
- `LCM(2, 15) = 30` 
- `LCM(2, 8) = 8`

## Implementations

### 1. Naive Method
```javascript
function naiveLCM(a, b) {
  let res = Math.max(a, b);
  while (true) {
    if (res % a === 0 && res % b === 0) {
      return res;
    }
    res++;
  }
}
```
Complexity: Time O(LCM(a,b) - max(a,b)), Space O(1)

2. Efficient Method Using GCD (Recommended)
```javascript
function gcd(a, b) {
  return b === 0 ? a : gcd(b, a % b);
}

function efficientLCM(a, b) {
  return (a * b) / gcd(a, b);
}
```
Complexity: Time O(log(min(a,b))), Space O(log(min(a,b)))

# How It Works
## The formula LCM(a,b) = (a × b) / GCD(a,b) works because:

GCD finds the largest common divisor

The product a×b counts all factors

Dividing by GCD removes the "overcounted" common factors

Example: LCM(4, 6)

GCD(4,6) = 2

LCM = (4 × 6)/2 = 12

Recommendation
Use the GCD-based method for best performance:

Extremely efficient: O(log(min(a,b))) time complexity

Works well even for very large numbers

Based on mathematical relationship between GCD and LCM