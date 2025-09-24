
# Mean and Median of an Array

Given an array `arr[]` of positive integers, find the **mean** and **median** of the array.  

- **Mean**: Average value of the array.  
- **Median**: Middle value after sorting the array. If the array has even length, median is the average of the two middle elements.  

**Note:** Return the **floor** value of both mean and median.

---

## Examples

**Example 1:**  

**Input:**  
`arr = [1, 2, 19, 28, 5]`  

**Output:**  
`11 5`  

**Explanation:**  
Mean = floor((1 + 2 + 19 + 28 + 5) / 5) = 11  
Median = middle element after sorting `[1, 2, 5, 19, 28]` → 5

---

**Example 2:**  

**Input:**  
`arr = [2, 8, 3, 4]`  

**Output:**  
`4 3`  

**Explanation:**  
Mean = floor((2 + 8 + 3 + 4) / 4) = 4  
Median = floor((3 + 4) / 2) = 3

---

## Constraints

- `1 ≤ arr.length ≤ 10^5`  
- `1 ≤ arr[i] ≤ 10^4`  

---

## JavaScript Implementation

```javascript
class Solution {
    
    mean(arr) {
        let n = arr.length;
        let sum = this.sum(arr, n);
        return Math.floor(sum / n);
    }

    median(arr) {
        let n = arr.length;
        arr.sort((a, b) => a - b);

        if (n % 2 !== 0) {
            return arr[Math.floor(n / 2)];
        } else {
            let mid1 = arr[n / 2 - 1];
            let mid2 = arr[n / 2];
            return Math.floor((mid1 + mid2) / 2);
        }
    }

    sum(arr, n) {
        let sum = 0;
        for (let i = 0; i < n; i++) {
            sum += arr[i];
        }
        return sum;
    }
}

// Test Cases
let obj = new Solution();
console.log(obj.mean([1, 2, 19, 28, 5]), obj.median([1, 2, 19, 28, 5])); // Output: 11 5
console.log(obj.mean([2, 8, 3, 4]), obj.median([2, 8, 3, 4]));             // Output: 4 3
````

**Time Complexity:**

* Mean: O(n)
* Median: O(n log n) (due to sorting)

**Space Complexity:** O(1) (in-place sorting if allowed)

