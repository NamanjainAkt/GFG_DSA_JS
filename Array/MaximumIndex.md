
# Maximum Index Difference in an Array

Given an array `arr` of positive integers, the task is to **find the maximum value of `j - i`** such that:

- `arr[i] < arr[j]`  
- `i < j`

---

## Examples

**Example 1:**  

**Input:**  
`arr = [1, 10]`  

**Output:**  
`1`  

**Explanation:**  
`arr[0] < arr[1]` → `j - i = 1 - 0 = 1`

---

**Example 2:**  

**Input:**  
`arr = [5, 4, 3]`  

**Output:**  
`0`  

**Explanation:**  
No pair satisfies `arr[i] < arr[j]`.

---

**Example 3:**  

**Input:**  
`arr = [34, 8, 10, 3, 2, 80, 30, 33, 1]`  

**Output:**  
`6`  

**Explanation:**  
`arr[1] < arr[7]` → `j - i = 7 - 1 = 6`

---

## Constraints

- `1 ≤ arr.length ≤ 10^5`  
- `0 ≤ arr[i] ≤ 10^9`  

---

## Efficient Approach (Using Preprocessing)

**Steps:**

1. Create an array `LMin[]` such that `LMin[i]` stores the **minimum element from `arr[0]` to `arr[i]`**.  
2. Create an array `RMax[]` such that `RMax[j]` stores the **maximum element from `arr[j]` to `arr[n-1]`**.  
3. Use two pointers `i` and `j` starting from 0:
    - If `LMin[i] <= RMax[j]`, update `maxDiff = max(maxDiff, j - i)` and increment `j`.  
    - Else increment `i`.
4. Stop when either pointer reaches the end.

**Time Complexity:** O(n)  
**Space Complexity:** O(n)

---

## Code Implementation (JavaScript)

```javascript
class Solution {
    maxIndexDiff(arr) {
        let n = arr.length;
        if (n === 0) return 0;

        // Step 1: LMin array
        const LMin = Array(n);
        LMin[0] = arr[0];
        for (let i = 1; i < n; i++) {
            LMin[i] = Math.min(arr[i], LMin[i - 1]);
        }

        // Step 2: RMax array
        const RMax = Array(n);
        RMax[n - 1] = arr[n - 1];
        for (let j = n - 2; j >= 0; j--) {
            RMax[j] = Math.max(arr[j], RMax[j + 1]);
        }

        // Step 3: Two pointers
        let i = 0, j = 0, maxDiff = 0;
        while (i < n && j < n) {
            if (LMin[i] <= RMax[j]) {
                maxDiff = Math.max(maxDiff, j - i);
                j++;
            } else {
                i++;
            }
        }

        return maxDiff;
    }
}

// Test Cases
let obj = new Solution();
console.log(obj.maxIndexDiff([1, 10]));                 // Output: 1
console.log(obj.maxIndexDiff([5, 4, 3]));               // Output: 0
console.log(obj.maxIndexDiff([34, 8, 10, 3, 2, 80, 30, 33, 1])); // Output: 6