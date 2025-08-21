# 📘 Geometric Progression (GP) – Find the nth Term

## 💡 Problem Statement

Given the **first two terms** of a Geometric Series (`a` and `b`), and a positive integer `n`, the task is to find the **nth term** of the series.

A Geometric Progression is a sequence where each term after the first is found by multiplying the previous one by a constant known as the **common ratio**.

---

## 🧮 Formula

To find the nth term of a GP:

```
Tn = a * r^(n-1)
```

Where:
- `a` is the first term
- `r` is the common ratio (calculated as `b / a`)
- `n` is the term number
- `^` denotes exponentiation

---

## ✅ Constraints

- `-100 ≤ a, b ≤ 100`
- `1 ≤ n ≤ 9`

---

## 📥 Input Examples

### Example 1
```js
a = 2
b = 3
n = 1
```
**Output**: `2`  
**Explanation**: First term is 2, so the 1st term is simply `a`.

### Example 2
```js
a = 1
b = 2
n = 5
```
**Output**: `16`  
**Explanation**: Common ratio `r = b/a = 2`, so:  
`T5 = 1 * (2)^(5-1) = 1 * 16 = 16`

---

## 🧑‍💻 JavaScript Implementation

```js
/**
 * @param {number} a - First term of the GP
 * @param {number} b - Second term of the GP
 * @param {number} n - Term number to find
 * @returns {number} - nth term of the GP
 */
class Solution {
    termOfGp(a, b, n) {
        // Calculate common ratio
        let r = b / a;

        // Calculate nth term using the formula: a * r^(n-1)
        let val = Math.pow(r, n - 1);
        let res = a * val;

        return res;
    }
}