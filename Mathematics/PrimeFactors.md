# Prime Factorization

## Overview
Prime factorization is the process of finding which prime numbers multiply together to make the original number. Every number has a unique prime factorization.

### Key Properties
- Unique factorization: Each number has exactly one set of prime factors
- 1 is neither prime nor composite
- Prime factorizations help with divisibility, fractions, and cryptography
- Numbers can be expressed as products of prime powers (e.g., 450 = 2 × 3² × 5²)

## Examples
- 12 → 2 × 2 × 3
- 315 → 3 × 3 × 5 × 7

## Implementations

### 1. Naive Solution (Using isPrime function)
```javascript
function isPrime(num) {
  if (num <= 1) return false;
  if (num === 2) return true;
  if (num % 2 === 0) return false;
  for (let i = 3; i * i <= num; i += 2) {
    if (num % i === 0) return false;
  }
  return true;
}

function printPrimeFactors(n) {
  for (let i = 2; i < n; i++) {
    if (isPrime(i)) {
      let x = i;
      while (n % x === 0) {
        console.log(i);
        x = x * i;
      }
    }
  }
}
```
- Complexity: Time O(n³/² × log n), Space O(1)

### 2. Efficient Solution (Recommended)

```javascript
function primeFactors(n) {
  // Handle factors of 2
  while (n % 2 === 0) {
    console.log(2);
    n = n / 2;
  }
  
  // Handle odd factors
  for (let i = 3; i * i <= n; i += 2) {
    while (n % i === 0) {
      console.log(i);
      n = n / i;
    }
  }
  
  // Handle remaining prime
  if (n > 2) console.log(n);
}
```
- Complexity: Time O(√n × log n), Space O(1)

### 3. Most Efficient Solution (6k ± 1 optimization)

```javascript
function printPrimeFactors(n) {
  if (n <= 1) return;
  
  // Handle factors of 2
  while (n % 2 === 0) {
    console.log(2);
    n = n / 2;
  }
  
  // Handle factors of 3
  while (n % 3 === 0) {
    console.log(3);
    n = n / 3;
  }
  
  // Handle factors of form 6k ± 1
  for (let i = 5; i * i <= n; i += 6) {
    while (n % i === 0) {
      console.log(i);
      n = n / i;
    }
    while (n % (i + 2) === 0) {
      console.log(i + 2);
      n = n / (i + 2);
    }
  }
  
  // Handle remaining prime
  if (n > 3) console.log(n);
}
```

- Complexity: Time O(√n × log n), Space O(1)

### How It Works
1. Remove factors of 2 (the only even prime)

2. Check odd factors up to √n

3. Optimized version skips numbers divisible by 2 or 3 using 6k ± 1 pattern

4. Final check for any remaining prime factor

### Recommendation
#### Use the Efficient Solution for most cases:

- Simple to implement

- Good performance for most numbers

- Time complexity O(√n × log n)

#### Use the Most Efficient Solution for performance-critical applications:

- Best for very large numbers

- Uses mathematical optimizations

- Same time complexity with better constant factors