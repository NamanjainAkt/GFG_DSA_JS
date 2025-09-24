
# Check Palindrome Using Recursion

A **palindrome** is a string that reads the same forwards and backwards.

---

## Examples

- `"ABBA"` → Palindrome  
- `"GEEKS"` → Not a palindrome  
- `"abcba"` → Palindrome  

---

## Recursive Approach

**Steps:**

1. **Base Case:**  
   - If the string length is 0 or 1, return `true`.
2. **Recursive Case:**  
   - Check if the first and last characters are equal.  
   - Recursively check the substring excluding the first and last characters.  
   - Return `true` only if both conditions are satisfied.

---

### Implementation

```js
function isPal(s, start, end) {
    if (start >= end) return true; // Base case: 0 or 1 char left
    return (s[start] == s[end]) && isPal(s, start + 1, end - 1);
}

// Driver code
console.log(isPal("abcba", 0, 4));  // true
console.log(isPal("abba", 0, 3));   // true
console.log(isPal("geeks", 0, 4));  // false
````

---

## How It Works

* For `"ABBA"`:

  ```
  Compare 'A' and 'A' → equal
  Recurse on "BB"
  Compare 'B' and 'B' → equal
  Recurse on "" → base case → true
  ```
* For `"ABCD"`:

  ```
  Compare 'A' and 'D' → not equal → false
  ```

---

## Complexity

* **Time Complexity:** O(n)

  * Each recursive call checks two characters.
  * Recurrence: T(n) = T(n-2) + Θ(1)
* **Auxiliary Space:** O(n) (recursion stack)

  * Iterative solution can reduce it to O(1).

---

## Summary

* Recursion breaks the problem into smaller subproblems.
* Returns `false` early on mismatch.
* Base cases handle empty or single-character strings.
* Elegant and clear, but uses extra stack space compared to iterative methods.
