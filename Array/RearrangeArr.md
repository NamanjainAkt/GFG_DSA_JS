
# Rearrange Array as arr[arr[i]]

Given an array `arr[]` of size `n` where every element is in the range from `0` to `n-1`.  
Rearrange the array **in-place** so that `arr[i]` becomes `arr[arr[i]]`.

---

## Examples

**Example 1:**  

**Input:**  
`arr = [1, 0]`  

**Output:**  
`[0, 1]`  

**Explanation:**  
- `arr[arr[0]] = arr[1] = 0`  
- `arr[arr[1]] = arr[0] = 1`  
So the transformed array becomes `[0, 1]`.

---

**Example 2:**  

**Input:**  
`arr = [4, 0, 2, 1, 3]`  

**Output:**  
`[3, 4, 2, 0, 1]`  

**Explanation:**  
- `arr[arr[0]] = arr[4] = 3`  
- `arr[arr[1]] = arr[0] = 4`  
- `arr[arr[2]] = arr[2] = 2`  
- `arr[arr[3]] = arr[1] = 0`  
- `arr[arr[4]] = arr[3] = 1`  

---

## Constraints

- `1 ≤ n ≤ 10^5`  
- `0 ≤ arr[i] < n`  

---

## JavaScript Implementation (In-place)

```javascript
class Solution {
    arrange(arr) {
        let n = arr.length;

        // Step 1: Store both old and new values in arr[i]
        for (let i = 0; i < n; i++) {
            arr[i] = arr[i] + (arr[arr[i]] % n) * n;
        }

        // Step 2: Extract the new values
        for (let i = 0; i < n; i++) {
            arr[i] = Math.floor(arr[i] / n);
        }

        return arr;
    }
}

// Test Cases
let obj = new Solution();
console.log(obj.arrange([1, 0]));            // [0, 1]
console.log(obj.arrange([4, 0, 2, 1, 3]));  // [3, 4, 2, 0, 1]
````

**Time Complexity:** O(n) — single traversal to encode and decode values.
**Space Complexity:** O(1) — in-place rearrangement without extra space.

