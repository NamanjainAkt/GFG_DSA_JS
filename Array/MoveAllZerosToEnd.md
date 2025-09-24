
# Move All 0s to End of Array

Given an array of `n` numbers, move all the 0s to the end of the array while maintaining the relative order of the non-zero elements.

---

## Examples

**Input:**  
[10, 0, 0, 7, 0, 8]  
**Output:**  
[10, 7, 8, 0, 0, 0]  

**Input:**  
[0, 0, 0, 3]  
**Output:**  
[3, 0, 0, 0]  

---

## Edge Cases
- All elements are zero → no change  
  `[0, 0, 0] → [0, 0, 0]`  
- All elements are non-zero → no change  
  `[1, 2, 3] → [1, 2, 3]`  

---

## Naive Approach (O(N²))

- Traverse array left to right.  
- If `arr[i] == 0`, search to the right for the first non-zero element.  
- Swap and continue.  

### Implementation

```javascript
function moveZerosToEnd(arr) {
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] === 0) {
            for (let j = i + 1; j < arr.length; j++) {
                if (arr[j] !== 0) {
                    [arr[i], arr[j]] = [arr[j], arr[i]];
                    break;
                }
            }
        }
    }
    return arr;
}

// Sample Test
let arr1 = [10, 0, 0, 7, 8, 0];
console.log("Naive Approach Output:");
console.log(moveZerosToEnd([...arr1])); // [10, 7, 8, 0, 0, 0]
````

**Time Complexity:** O(N²)
**Space Complexity:** O(1)

---

## Optimal Approach (O(N), Two Pointer)

* Use `count` to track the position for the next non-zero.
* Traverse array:

  * If `arr[i] != 0`, swap with `arr[count]`, increment `count`.
  * If zero, skip.
* At the end, all non-zeros are shifted forward, zeros pushed to end.

### Implementation

```javascript
function moveZeros(arr) {
    let count = 0;
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] !== 0) {
            [arr[i], arr[count]] = [arr[count], arr[i]];
            count++;
        }
    }
    return arr;
}

// Sample Test
let arr2 = [10, 8, 0, 0, 12, 0];
console.log("Optimal Approach Output:");
console.log(moveZeros([...arr2])); // [10, 8, 12, 0, 0, 0]
```

**Time Complexity:** O(N)
**Space Complexity:** O(1)

---

✅ **Summary:**

* **Naive Approach:** Works but slow (O(N²)).
* **Optimal Approach:** Best choice using two-pointer method.



