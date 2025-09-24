
# Insert a Value at the End of Array

You are given an array `arr` (not completely filled) and a value `val`.  
The task is to insert the value at the **end of the array**.

---

## Examples

**Input:**  
`arr = [1, 2, 3, 4, 5], val = 90`  
**Output:**  
`[1, 2, 3, 4, 5, 90]`  

**Explanation:**  
After inserting 90 at the end → array becomes `[1, 2, 3, 4, 5, 90]`.

---

**Input:**  
`arr = [1, 2, 3], val = 50`  
**Output:**  
`[1, 2, 3, 50]`  

**Explanation:**  
After inserting 50 at the end → array becomes `[1, 2, 3, 50]`.

---

## Constraints
- `1 ≤ arr.size() ≤ 10^5`  
- `0 ≤ arr[i], val ≤ 10^6`  

---

## Code Implementation (JavaScript)

```javascript
/**
 * @param {number[]} arr
 * @param {number} val
 */
class Solution {
    insertAtEnd(arr, val) {
        // Insert at the end
        arr.push(val);
        return arr;
    }
}

// Test cases
let obj = new Solution();

console.log(obj.insertAtEnd([1, 2, 3, 4, 5], 90)); 
// Output: [1, 2, 3, 4, 5, 90]

console.log(obj.insertAtEnd([1, 2, 3], 50)); 
// Output: [1, 2, 3, 50]
````

---

## Time & Space Complexity

* **Time Complexity:** O(1) → Adding at the end takes constant time (amortized).
* **Space Complexity:** O(1) → No extra space used.
