
# Reverse Array in Groups

Given an array `arr[]` of positive integers, reverse every sub-array group of size `k`.  

**Note:** If `k` is greater than or equal to the array size, reverse the entire array.

---

## Examples

**Example 1:**  

**Input:**  
`arr = [1, 2, 3, 4, 5], k = 3`  

**Output:**  
`[3, 2, 1, 5, 4]`  

**Explanation:**  
- First group: `[1, 2, 3]` → reversed → `[3, 2, 1]`  
- Second group: `[4, 5]` → reversed → `[5, 4]`  

---

**Example 2:**  

**Input:**  
`arr = [5, 6, 8, 9], k = 5`  

**Output:**  
`[9, 8, 6, 5]`  

**Explanation:**  
Since `k` is greater than array size, the entire array is reversed.

---

## Constraints

- `1 ≤ arr.length, k ≤ 10^5`  
- `1 ≤ arr[i] ≤ 10^5`  

---

## JavaScript Implementation

```javascript
class Solution {
    reverseInGroups(arr, k) {
        let n = arr.length;
        
        if (k >= n) return arr.reverse(); // Reverse entire array if k >= n
        if (k === 1) return arr;          // No need to reverse if k = 1

        for (let i = 0; i < n; i += k) {
            let left = i;
            let right = Math.min(i + k - 1, n - 1);
            let swaps = Math.floor((right - left + 1) / 2);

            for (let j = 0; j < swaps; j++) {
                let temp = arr[left + j];
                arr[left + j] = arr[right - j];
                arr[right - j] = temp;
            }
        }

        return arr;
    }
}

// Test Cases
let obj = new Solution();
console.log(obj.reverseInGroups([1, 2, 3, 4, 5], 3)); // [3, 2, 1, 5, 4]
console.log(obj.reverseInGroups([5, 6, 8, 9], 5));    // [9, 8, 6, 5]
````

**Time Complexity:** O(n) — each element is visited at most once.
**Space Complexity:** O(1) — in-place reversal without extra space.
