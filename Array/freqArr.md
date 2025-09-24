
# More Frequent Element

Given an array `arr[]` and two elements `x` and `y`, return the element that occurs more frequently.  

- If both elements have the same frequency, return the smaller one.

---

## Examples

**Example 1:**  

**Input:**  
`arr[] = [1, 1, 2, 2, 3, 3, 4, 4, 4, 4, 5], x = 4, y = 5`  

**Output:**  
`4`  

**Explanation:**  
- Frequency of 4 is 4  
- Frequency of 5 is 1  
- Since 4 > 1, return 4  

---

**Example 2:**  

**Input:**  
`arr[] = [1, 2, 3, 4, 5, 6, 7, 8], x = 1, y = 7`  

**Output:**  
`1`  

**Explanation:**  
- Frequency of 1 is 1  
- Frequency of 7 is 1  
- Since both have the same frequency, return the smaller one → 1  

---

## Constraints

- `1 ≤ arr.size() ≤ 10^6`  
- `0 ≤ arr[i], x, y ≤ 10^8`

---

## JavaScript Implementation

```javascript
class Solution {
    moreFrequent(arr, x, y) {
        let freqX = 0, freqY = 0;

        for (let j = 0; j < arr.length; j++) {
            if (arr[j] === x) freqX++;
            if (arr[j] === y) freqY++;
        }

        if (freqX === freqY) return Math.min(x, y);
        return freqX > freqY ? x : y;
    }
}

// Test Cases
let obj = new Solution();
console.log(obj.moreFrequent([1,1,2,2,3,3,4,4,4,4,5], 4, 5)); // 4
console.log(obj.moreFrequent([1,2,3,4,5,6,7,8], 1, 7));       // 1
````

**Time Complexity:** O(n)
**Space Complexity:** O(1)
