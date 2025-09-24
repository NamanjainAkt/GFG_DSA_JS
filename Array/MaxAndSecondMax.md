
# Maximum and Second Maximum in an Array

Given an array `arr[]` of positive integers (may have duplicates), the task is to **find the maximum and second maximum elements** such that:

- Both elements are **distinct**.
- If no second maximum exists, return `-1` as the second maximum.

---

## Examples

**Example 1:**  

**Input:**  
`arr = [2, 1, 2]`  

**Output:**  
`[2, 1]`  

**Explanation:**  
Maximum = 2, second maximum = 1

---

**Example 2:**  

**Input:**  
`arr = [3, 3, 3]`  

**Output:**  
`[3, -1]`  

**Explanation:**  
Maximum = 3, no distinct smaller element exists, so second maximum = -1

---

## Constraints

- `1 ≤ arr.length ≤ 10^5`  
- `1 ≤ arr[i] ≤ 10^6`  

---

## Efficient Approach (Single Traversal)

**Steps:**

1. Initialize `firstMax = -1` and `secondMax = -1`.  
2. Traverse the array:
    - If `arr[i] > firstMax`:  
        - `secondMax = firstMax`  
        - `firstMax = arr[i]`
    - Else if `arr[i] > secondMax && arr[i] < firstMax`:  
        - `secondMax = arr[i]`
3. Return `[firstMax, secondMax]`.

**Time Complexity:** O(n)  
**Space Complexity:** O(1)

---

## JavaScript Implementation

```javascript
class Solution {
    largestAndSecondLargest(arr) {
        let firstMax = -1;
        let secondMax = -1;

        for (let i = 0; i < arr.length; i++) {
            if (arr[i] > firstMax) {
                secondMax = firstMax;
                firstMax = arr[i];
            } else if (arr[i] > secondMax && arr[i] < firstMax) {
                secondMax = arr[i];
            }
        }

        return [firstMax, secondMax];
    }
}

// Test Cases
let obj = new Solution();
console.log(obj.largestAndSecondLargest([2, 1, 2])); // Output: [2, 1]
console.log(obj.largestAndSecondLargest([3, 3, 3])); // Output: [3, -1]
console.log(obj.largestAndSecondLargest([5, 1, 5, 3, 4])); // Output: [5, 4]
