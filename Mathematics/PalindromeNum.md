# Palindrome Number Checker

## 📌 Problem
A **palindrome number** is a number that remains the same when its digits are reversed.  
Example: `12321` → Palindrome, `1451` → Not a palindrome.

---

## 🔎 Approach
1. Reverse the number:
   - Extract last digit using `%`.
   - Build reversed number.
   - Remove last digit using `Math.floor()`.
2. Compare reversed number with the original:
   - If equal → Palindrome.
   - Else → Not a palindrome.

---

## ✅ Algorithm
1. Initialize `reverse = 0`, store original number in `temp`.
2. While `temp != 0`:
   - `digit = temp % 10`
   - `reverse = reverse * 10 + digit`
   - `temp = Math.floor(temp / 10)`
3. Compare `reverse` with `n`.

---

## 🧑‍💻 Code (JavaScript)
```javascript
function checkPalindrome(n) {
  let reverse = 0;
  let temp = n;
  while (temp !== 0) {
    reverse = (reverse * 10) + (temp % 10); 
    temp = Math.floor(temp / 10); 
  }
  return reverse === n; 
}

const n = 4553;
console.log(checkPalindrome(n) ? "Yes" : "No");
```

---

## ⏱ Complexity
- **Time:** `O(log₁₀(n))` → proportional to number of digits.  
- **Space:** `O(1)` → constant space.

---
