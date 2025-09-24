
# Remove Duplicates from a Sorted Array

Given a **sorted array**, the task is to remove the duplicate elements from the array.

---

## Examples

**Input:**  
`arr[] = {2, 2, 2, 2, 2}`  
**Output:**  
`arr[] = {2}`  
`new size = 1`  

**Input:**  
`arr[] = {1, 2, 2, 3, 4, 4, 4, 5, 5}`  
**Output:**  
`arr[] = {1, 2, 3, 4, 5}`  
`new size = 5`  

---

## Method 1: Using Extra Space

```javascript
function remDups(arr) {
    let temp = [arr[0]];
    let res = 1;
    for (let i = 1; i < arr.length; i++) {
        if (temp[res - 1] !== arr[i]) {
            temp[res] = arr[i];
            res++;
        }
    }
    for (let i = 0; i < res; i++) {
        arr[i] = temp[i];
    }
    return res;
}

let arr = [10, 20, 20, 30, 30, 30];
console.log("Before Removal: " + arr);
let n = remDups(arr);
console.log("After Removal: " + arr.slice(0, n));
````

**Output:**

```
Before Removal: 10 20 20 30 30 30
After Removal: 10 20 30
```

**Time Complexity:** O(n)
**Auxiliary Space:** O(n)

---

## Method 2: Constant Extra Space

```javascript
function remDups(arr) {
    let res = 1;
    for (let i = 1; i < arr.length; i++) {
        if (arr[res - 1] !== arr[i]) {
            arr[res] = arr[i];
            res++;
        }
    }
    return res;
}

let arr = [10, 20, 20, 30, 30, 30];
console.log("Before Removal: " + arr);
let n = remDups(arr);
console.log("After Removal: " + arr.slice(0, n));
```

**Output:**

```
Before Removal: 10 20 20 30 30 30
After Removal: 10 20 30
```

**Time Complexity:** O(n)
**Auxiliary Space:** O(1)
