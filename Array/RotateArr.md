
# Rotate Array Left by d Steps

Given an array `arr[]`, rotate the array to the left (counter-clockwise) by `d` steps **in-place**.

> Note: Consider the array as circular.

---

## Examples

**Example 1:**  

**Input:**  
`arr[] = [1, 2, 3, 4, 5], d = 2`  

**Output:**  
`[3, 4, 5, 1, 2]`  

**Explanation:**  
When rotated by 2 elements, the array becomes `[3, 4, 5, 1, 2]`.

---

**Example 2:**  

**Input:**  
`arr[] = [2, 4, 6, 8, 10, 12, 14, 16, 18, 20], d = 3`  

**Output:**  
`[8, 10, 12, 14, 16, 18, 20, 2, 4, 6]`

---

**Example 3:**  

**Input:**  
`arr[] = [7, 3, 9, 1], d = 9`  

**Output:**  
`[3, 9, 1, 7]`  

**Explanation:**  
Rotating 9 times is equivalent to rotating `9 % 4 = 1` time, resulting in `[3, 9, 1, 7]`.

---

## Constraints

- `1 <= arr.size(), d <= 10^5`  
- `0 <= arr[i] <= 10^5`

---

## JavaScript Implementation

```javascript
class Solution {
    // Function to rotate an array by d elements in counter-clockwise direction.
    rotateArr(arr, d) {
        let n = arr.length;
        let x = d % n; // In case d > n
        
        // Reverse first part
        this.reverse(arr, 0, x - 1);
        // Reverse second part
        this.reverse(arr, x, n - 1);
        // Reverse whole array
        this.reverse(arr, 0, n - 1);
        
        return arr;
    }

    reverse(arr, left, right) {
        while (left < right) {
            let temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;
            left++;
            right--;
        }
    }
}

// Test Cases
let obj = new Solution();
console.log(obj.rotateArr([1, 2, 3, 4, 5], 2));          // [3, 4, 5, 1, 2]
console.log(obj.rotateArr([2, 4, 6, 8, 10, 12, 14, 16, 18, 20], 3)); // [8,10,12,14,16,18,20,2,4,6]
console.log(obj.rotateArr([7, 3, 9, 1], 9));             // [3, 9, 1, 7]
````

**Time Complexity:** O(n)
**Space Complexity:** O(1) – in-place rotation using reversal method

