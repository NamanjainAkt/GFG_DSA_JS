
# Check if Array is Sorted in Ascending Order

Given an array of size `n`, write a program to check if it is sorted in ascending order or not.  
Equal values are allowed in an array and two consecutive equal values are considered sorted.

---

## Examples

**Input:**  
20 21 45 89 89 90  
**Output:**  
Yes  

**Input:**  
20 20 45 89 89 90  
**Output:**  
Yes  

**Input:**  
20 20 78 98 99 97  
**Output:**  
No  

---

## Naive Approach

- For each element `arr[i]`, check all elements to its right.  
- If any element `arr[j] (j > i)` is less than `arr[i]`, the array is not sorted.

### Steps:
1. Loop `i` from 0 to n-2  
2. Inner loop `j` from i+1 to n-1  
3. If `arr[j] < arr[i]`, return false  
4. If no violation found, return true  

### Implementation:

```javascript
function isSorted(arr) {
    for (let i = 0; i < arr.length; i++) {
        for (let j = i + 1; j < arr.length; j++) {
            if (arr[j] < arr[i]) {
                return false;
            }
        }
    }
    return true;
}

let arr = [7, 2, 30, 10];
console.log(isSorted(arr) ? "true" : "false");
````

**Output:**

```
false
```

**Time Complexity:** O(N²)
**Space Complexity:** O(1)

---

## Iterative Approach (Efficient)

* Check each element with its previous one.
* If any `arr[i] < arr[i-1]`, the array is not sorted.

### Steps:

1. Loop `i` from 1 to n-1
2. If `arr[i] < arr[i-1]`, return false
3. If loop completes, return true

### Implementation:

```javascript
function arraySortedOrNot(arr) {
    if (arr.length === 0 || arr.length === 1) {
        return true;
    }
    for (let i = 1; i < arr.length; i++) {
        if (arr[i - 1] > arr[i]) {
            return false;
        }
    }
    return true;
}

let arr = [20, 23, 23, 45, 78, 88];
if (arraySortedOrNot(arr)) {
    console.log("Yes");
} else {
    console.log("No");
}
```

**Output:**

```
Yes
```

**Time Complexity:** O(N)
**Space Complexity:** O(1)


