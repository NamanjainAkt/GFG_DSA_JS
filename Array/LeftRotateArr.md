
# Left Rotate an Array by One

Given an array of integers `arr[]` of size `N`, the task is to rotate the array elements to the left by one position.  

---

## What is Left Rotation?
- Move all elements **one position to the left**.  
- Send the **first element** to the end.  

Visualize the array as arranged in a **circle**, and we are rotating counterclockwise.  

---

## Examples

**Input:** `arr = [1, 2, 3, 4, 5]`  
**Output:** `arr = [2, 3, 4, 5, 1]`  

**Input:** `arr = [30, 5, 20]`  
**Output:** `arr = [5, 20, 30]`  

**Input:** `arr = [10]`  
**Output:** `arr = [10]`  

---

## Naive Solution (Using Extra Space)

**Steps:**
1. Create a temporary array.  
2. Copy elements from index `1` onward into it.  
3. Append the first element at the end.  
4. Copy the temp array back to the original array.  

**Dry Run**  
Input: `[1, 2, 3, 4, 5]`  
- Temp = `[2, 3, 4, 5]`  
- Append first element → Temp = `[2, 3, 4, 5, 1]`  
- Copy back → Final = `[2, 3, 4, 5, 1]`  

**Time Complexity:** O(n)  
**Space Complexity:** O(n)  

---

## Efficient Solution (In-Place)

**Steps:**
1. Store the first element in a temporary variable.  
2. Shift all elements one position to the left.  
3. Place the stored element at the end.  

**Dry Run**  
Input: `[1, 2, 3, 4, 5]`  
- Store `x = 1`  
- Shift elements: `[2, 3, 4, 5, 5]`  
- Place `x` at the end → `[2, 3, 4, 5, 1]`  

---

## Code (Efficient Approach)

```javascript
function leftRotateEfficient(arr) {
    let n = arr.length;
    let x = arr[0]; // store first element
    
    for (let i = 1; i < n; i++) {
        arr[i - 1] = arr[i]; // shift elements left
    }
    arr[n - 1] = x; // put first element at end
}

let arr = [1, 2, 3, 4, 5];
leftRotateEfficient(arr);
console.log("Rotated Array:", arr);
````

**Output:**

```
Rotated Array: [2, 3, 4, 5, 1]
```

**Time Complexity:** Θ(n)
**Space Complexity:** Θ(1) (only one variable used)

