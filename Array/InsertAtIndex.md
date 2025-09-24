
# Insert an Element at Given Index in Array

You are given an array `arr` (0-based index) and two positive integers `index` and `val`.  
You need to insert `val` at the given index.

---

## Examples

**Input:**  
`arr = [1, 2, 3, 4, 5], index = 5, val = 90`  
**Output:**  
`[1, 2, 3, 4, 5, 90]`  

**Explanation:**  
90 is inserted at index `5` (end).  

---

**Input:**  
`arr = [1, 2, 3, 4, 5], index = 2, val = 90`  
**Output:**  
`[1, 2, 90, 3, 4, 5]`  

**Explanation:**  
90 is inserted at index `2` (0-based indexing).  

---

## Constraints
- `1 ≤ arr.size() ≤ 10^5`  
- `0 ≤ arr[i], val ≤ 10^6`  
- `0 ≤ index ≤ arr.size()`  

---

## Code Implementation (JavaScript)

```javascript
/**
 * @param {number[]} arr
 * @param {number} index
 * @param {number} val
 */
class Solution {
    insertAtIndex(arr, index, val) {
        // splice(start, deleteCount, itemToAdd)
        arr.splice(index, 0, val);
        return arr;
    }
}

// Test cases
let obj = new Solution();

console.log(obj.insertAtIndex([1, 2, 3, 4, 5], 5, 90)); 
// Output: [1, 2, 3, 4, 5, 90]

console.log(obj.insertAtIndex([1, 2, 3, 4, 5], 2, 90)); 
// Output: [1, 2, 90, 3, 4, 5]
````

---

## Time & Space Complexity

* **Time Complexity:** O(n) → Because elements after `index` need to be shifted.
* **Space Complexity:** O(1) → Done in place.


