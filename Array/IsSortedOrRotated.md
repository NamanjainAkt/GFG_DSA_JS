
# Check if an Array is Sorted and Rotated

Given an array `arr[]` of **distinct positive integers**, determine if it is **sorted (increasing or decreasing) and then rotated at least once** in the counter-clockwise direction.  

**Note:** A purely sorted array is **not** considered rotated.

---

## Examples

**Example 1:**  

**Input:**  
`arr = [3, 4, 1, 2]`  

**Output:**  
`true`  

**Explanation:**  
Original sorted array `[1, 2, 3, 4]` is rotated twice → `[3, 4, 1, 2]`

---

**Example 2:**  

**Input:**  
`arr = [1, 2, 3]`  

**Output:**  
`false`  

**Explanation:**  
Array is sorted but not rotated.

---

**Example 3:**  

**Input:**  
`arr = [5, 4, 3]`  

**Output:**  
`false`  

**Explanation:**  
Array is sorted in decreasing order but not rotated.

---

## Constraints

- `1 ≤ arr.length ≤ 10^6`  
- `1 ≤ arr[i] ≤ 10^6`  

---

## JavaScript Implementation

```javascript
class Solution {
    isSortedRotated(arr) {
        let n = arr.length;
        let ascDrop = 0, descDrop = 0;
        let ascBreakIndex = 0, descBreakIndex = 0;

        // Check for increasing sorted array with rotation
        for (let i = 0; i < n; i++) {
            let next = arr[(i + 1) % n];
            if (arr[i] > next) {
                ascDrop++;
                ascBreakIndex = i;
            }
        }

        // Check for decreasing sorted array with rotation
        for (let i = 0; i < n; i++) {
            let next = arr[(i + 1) % n];
            if (arr[i] < next) {
                descDrop++;
                descBreakIndex = i;
            }
        }

        // If fully sorted (no drops), not rotated
        if (ascDrop === 0 || descDrop === 0) return false;

        // If exactly one drop and not at last index, it is rotated
        if ((ascDrop === 1 && ascBreakIndex !== n - 1) || 
            (descDrop === 1 && descBreakIndex !== n - 1)) return true;

        return false;
    }
}

// Test Cases
let obj = new Solution();
console.log(obj.isSortedRotated([3, 4, 1, 2])); // true
console.log(obj.isSortedRotated([1, 2, 3]));    // false
console.log(obj.isSortedRotated([5, 4, 3]));    // false
````

**Time Complexity:** O(n) — single pass to count drops in both increasing and decreasing scenarios.
**Space Complexity:** O(1) — only a few variables used.
