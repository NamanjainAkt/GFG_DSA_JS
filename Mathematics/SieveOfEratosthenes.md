# Sieve of Eratosthenes

## Overview
The Sieve of Eratosthenes is an efficient algorithm to find all prime numbers up to a given limit `n`. It works by iteratively marking the multiples of each prime number starting from 2.

## Examples
- `n = 10` → 2, 3, 5, 7
- `n = 20` → 2, 3, 5, 7, 11, 13, 17, 19

## Implementation

### Efficient Approach (Sieve of Eratosthenes)
```javascript
function sieveOfEratosthenes(n) {
  // Create boolean array of size n+1, initially all true
  let prime = new Array(n + 1).fill(true);
  
  // Mark 0 and 1 as non-prime
  prime[0] = prime[1] = false;
  
  // Iterate from 2 to √n
  for (let p = 2; p * p <= n; p++) {
    // If prime[p] is not changed, then it's a prime
    if (prime[p]) {
      // Mark all multiples of p starting from p²
      for (let i = p * p; i <= n; i += p) {
        prime[i] = false;
      }
    }
  }
  
  // Collect all primes
  let result = [];
  for (let p = 2; p <= n; p++) {
    if (prime[p]) {
      result.push(p);
    }
  }
  
  return result;
}
```
### Complexity:

- Time: O(n log log n) - Nearly linear time

- Space: O(n) - For the boolean array

### How It Works
1. Initialize: Create a boolean array where each index represents a number

2. Mark non-primes: Start with 2, mark all its multiples as non-prime

3. Move to next prime: Find the next unmarked number (prime) and mark its multiples

4. Repeat: Continue until reaching √n

5. Collect results: All unmarked numbers are primes

### Key Optimizations
- Start marking multiples from p² (smaller multiples are already marked)

- Only iterate up to √n (all composites beyond this are already marked)

- Skip even numbers after 2 (can be added as an optimization)

### Recommendation
- Use the Sieve of Eratosthenes when:

- You need all primes up to a limit (not just checking one number)

- n is reasonably sized (up to ~10 million)

- You value time efficiency over space