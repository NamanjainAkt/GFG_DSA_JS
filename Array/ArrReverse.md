
# Reverse an Array In-Place

Given an array of size `n`, write a program to reverse the array in-place.

---

## Examples

**Input:**  
arr = {1, 2, 3}  
**Output:**  
arr = {3, 2, 1}  

**Input:**  
arr = {4, 5, 1, 2}  
**Output:**  
arr = {2, 1, 5, 4}  

---

## Naive Approach

- Create a temporary array.  
- Traverse the original array from end to start and store elements in temp.  
- Copy elements back from temp to the original array.  

### Implementation

```javascript
function reverseNaive(arr) {
    const temp = [];
    for (let i = arr.length - 1; i >= 0; i--) {
        temp.push(arr[i]);
    }
    for (let i = 0; i < arr.length; i++) {
        arr[i] = temp[i];
    }
    return arr; // Optional: for output purposes
}

// Test cases
console.log(reverseNaive([10, 20, 30])); // [30, 20, 10]
console.log(reverseNaive([1, 2]));       // [2, 1]
console.log(reverseNaive([]));           // []
````

**Output:**

```
[30, 20, 10]  
[2, 1]  
[]  
```

**Time Complexity:** O(N)
**Space Complexity:** O(N)

---

## Optimized Approach (Two-Pointer)

* Initialize two pointers:
  `low = 0` (start of array), `high = n-1` (end of array).
* While `low < high`, swap `arr[low]` and `arr[high]`.
* Increment `low`, decrement `high`.
* Stop when `low >= high`.

### Implementation

```javascript
function reverseArray(arr) {
    let low = 0;
    let high = arr.length - 1;

    while (low < high) {
        [arr[low], arr[high]] = [arr[high], arr[low]]; // Swap
        low++;
        high--;
    }
    return arr;
}

// Test cases
console.log(reverseArray([10, 20, 30, 40])); // [40, 30, 20, 10]
console.log(reverseArray([5]));              // [5]
console.log(reverseArray([]));               // []
```

**Output:**

```
[40, 30, 20, 10]  
[5]  
[]  
```

**Time Complexity:** O(N)
**Space Complexity:** O(1)

---

## Built-in Method in JavaScript

JavaScript arrays come with a built-in `.reverse()` method that modifies the array **in-place**.

```javascript
const arr = [10, 20, 30];
arr.reverse();
console.log(arr);  // [30, 20, 10]
```

---

✅ **Summary:**

* **Naive Approach:** Uses extra space (O(N)).
* **Two-Pointer Approach:** In-place, best method.
* **Built-in `.reverse()`:** Simplest solution, also in-place.


