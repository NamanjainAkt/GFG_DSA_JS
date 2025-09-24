

# 🔎 Find Largest Element in Array

## ✅ Problem

Given an array `arr` of size `N`, find the largest element.

---

## 📌 Example

```
Input : arr = [10, 20, 4]
Output: 20

Input : arr = [20, 10, 20, 4, 100]
Output: 100
```

---

## 🔹 Approach 1 – Naive Method (O(n²))

👉 Idea:

* For each element, assume it’s the largest.
* Compare it with all others.
* If it survives all comparisons → it’s the largest.

```js
function getLargest(arr, n) {
    for (let i = 0; i < n; ++i) {
        let flag = true;
        for (let j = i; j < n; ++j) {
            if (arr[j] > arr[i]) {
                flag = false;
                break;
            }
        }
        if (flag) {
            return arr[i];
        }
    }
    return -1;
}

let arr1 = [5, 8, 20, 15];
console.log("Largest in given array is " + getLargest(arr1, 4));
```

✅ Output

```
Largest in given array is 20
```

⏱ **Time Complexity**: `O(n²)` (two nested loops)
💾 **Space Complexity**: `O(1)`

---

## 🔹 Approach 2 – Linear Traversal (O(n)) ✅ Efficient

👉 Idea:

* Keep track of current maximum while traversing once.

```js
function largest(arr) {
    let max = arr[0];   // assume first is max
    for (let i = 1; i < arr.length; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    return max;
}

let arr2 = [10, 324, 45, 90, 9808];
console.log("Largest in given array is " + largest(arr2));
```

✅ Output

```
Largest in given array is 9808
```

⏱ **Time Complexity**: `O(n)` (single traversal)
💾 **Space Complexity**: `O(1)`

---

📖 **Summary**

* Naive → `O(n²)`, not practical.
* Linear traversal → `O(n)`, best for this problem.

---

