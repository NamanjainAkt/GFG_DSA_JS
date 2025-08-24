# Trailing Zeros in Factorial

## 📌 Problem
Count the number of **trailing zeros** in `n!` (factorial of n).  
Trailing zeros are consecutive zeros at the end of a number.

---

## 🔎 Examples
- `n = 5` → `5! = 120` → **1** trailing zero  
- `n = 10` → `10! = 3628800` → **2** trailing zeros  
- `n = 100` → `100!` → **24** trailing zeros  

---

## ❌ Naive Method (Not Recommended)
1. Compute factorial `n!`.  
2. Count how many times it can be divided by 10.  

```javascript
function findTrailingZeros(n) {
  let fact = 1;
  for (let i = 2; i <= n; i++) {
    fact = fact * i;
  }
  let res = 0;
  while (fact % 10 === 0) {
    res++;
    fact = Math.floor(fact / 10);
  }
  return res;
}
```

⚠️ Issues:
- Factorials grow very fast → integer overflow.  
- Too slow for large `n`.  

---

## ✅ Efficient Method (Optimal)
### Key Insight:
- Trailing zeros come from factors of **10 = 2 × 5**.  
- In factorials, there are always more 2s than 5s.  
- So, we only need to count factors of **5**.

### Steps:
1. Count multiples of `5`, `25`, `125`, … up to `n`.  
2. Sum them up.  

### Code:
```javascript
function countTrailingZeros(n) {
  let res = 0;
  for (let i = 5; i <= n; i *= 5) {
    res += Math.floor(n / i);
  }
  return res;
}

const n = 100;
console.log(`Count of trailing 0s in ${n}! is ${countTrailingZeros(n)}`);
```

---

## 🧮 Example (n = 100)
- ⌊100 / 5⌋ = 20 (multiples of 5)  
- ⌊100 / 25⌋ = 4 (extra 5s from multiples of 25)  
- ⌊100 / 125⌋ = 0  
- **Total = 20 + 4 = 24**  

---

## ⏱ Complexity
- **Time:** `O(log₅ n)`  
- **Space:** `O(1)`  

⚡ Very efficient, works for huge `n` without overflow.  

---
