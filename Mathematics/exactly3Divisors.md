# Exactly 3 Divisors

## 📌 Problem Statement
Given a positive integer `n`, find how many numbers **less than or equal to `n`** have **exactly 3 divisors**.

### Example
```text
Input: n = 6
Output: 1
Explanation: Only 4 has divisors {1, 2, 4}
```

```text
Input: n = 10
Output: 2
Explanation: 4 and 9 have divisors {1, 2, 4} and {1, 3, 9}
```

---

## 🔎 Key Observation
- A number has **exactly 3 divisors** if and only if it is the **square of a prime**.  
  - Example:  
    - 4 = 2² → divisors {1, 2, 4}  
    - 9 = 3² → divisors {1, 3, 9}  
- Why?  
  - If n has exactly 3 divisors, they must be {1, p, p²}, meaning n = p² and `p` is prime.

So, the task reduces to:  
👉 **Count how many primes p exist such that p² ≤ n.**

---

## 🧮 Approach
1. Compute `limit = √n`.  
2. Generate all primes ≤ `limit` using **Sieve of Eratosthenes**.  
3. Count them.  
4. That count is the answer.

---

## ⏱ Complexity
- Sieve of Eratosthenes: `O(√n log log √n)`  
- Counting primes: `O(√n)`  
- Efficient for n ≤ 10⁹ since √n ≤ 31622.

---

## ✅ JavaScript Implementation
```javascript
class Solution {
    exactly3Divisors(n) {
        let limit = Math.floor(Math.sqrt(n));
        let isPrime = new Array(limit + 1).fill(true);
        isPrime[0] = isPrime[1] = false;

        // Sieve of Eratosthenes
        for (let i = 2; i * i <= limit; i++) {
            if (isPrime[i]) {
                for (let j = i * i; j <= limit; j += i) {
                    isPrime[j] = false;
                }
            }
        }

        // Count primes ≤ sqrt(n)
        let count = 0;
        for (let i = 2; i <= limit; i++) {
            if (isPrime[i]) count++;
        }
        return count;
    }
}

// Example
let sol = new Solution();
console.log(sol.exactly3Divisors(6));   // Output: 1
console.log(sol.exactly3Divisors(10));  // Output: 2
console.log(sol.exactly3Divisors(100)); // Output: 4 (4, 9, 25, 49)
```

---

## 📚 Notes
- Only **prime squares** matter, not any other numbers.  
- n can be as large as 10⁹, but since we only sieve up to √n, it remains efficient.  
- Memory usage is also light since we only need an array of size √n.
