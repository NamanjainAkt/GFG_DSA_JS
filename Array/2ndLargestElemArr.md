
---

# 🔎 Find Second Largest Element in Array

## ✅ Problem

Given an array of integers, find the **second largest distinct element**.
If it does not exist, return a message accordingly.

---

## 📌 Example

```
Input : [12, 35, 1, 10, 34, 1]
Output: 34

Input : [10, 5, 10]
Output: 5

Input : [10, 10, 10]
Output: The second largest does not exist
```

---

## 🔹 Approach 1 – Brute Force (Sorting)

👉 Idea:

* Sort array.
* Traverse backward to find first element smaller than max.

```js
function secondLargestBruteForce(arr) {
    if (arr.length < 2) return "The second largest does not exist";

    arr.sort((a, b) => a - b);   // ascending sort

    const largest = arr[arr.length - 1];
    let index = arr.length - 2;

    // skip duplicates
    while (index >= 0 && arr[index] === largest) {
        index--;
    }

    return index >= 0
        ? `The second largest element is ${arr[index]}`
        : "The second largest does not exist";
}

// Test
console.log(secondLargestBruteForce([12, 35, 1, 10, 34, 1]));
console.log(secondLargestBruteForce([10, 5, 10]));
console.log(secondLargestBruteForce([10, 10, 10]));
```

✅ Output

```
The second largest element is 34
The second largest element is 5
The second largest does not exist
```

⏱ Time: `O(n log n)`
💾 Space: `O(1)`

---

## 🔹 Approach 2 – Optimized (One Pass) ✅

👉 Idea:

* Track `firstMax` and `secondMax` in one traversal.

```js
function secondLargestOptimized(arr) {
    if (arr.length < 2) return "The second largest does not exist";

    let firstMax = -Infinity;
    let secondMax = -Infinity;

    for (let num of arr) {
        if (num > firstMax) {
            secondMax = firstMax;
            firstMax = num;
        } else if (num < firstMax && num > secondMax) {
            secondMax = num;
        }
    }

    return secondMax !== -Infinity
        ? `The second largest element is ${secondMax}`
        : "The second largest does not exist";
}

// Test
console.log(secondLargestOptimized([12, 35, 1, 10, 34, 1]));
console.log(secondLargestOptimized([10, 5, 10]));
console.log(secondLargestOptimized([10, 10, 10]));
```

✅ Output

```
The second largest element is 34
The second largest element is 5
The second largest does not exist
```

⏱ Time: `O(n)`
💾 Space: `O(1)`

---

📖 **Summary**

* Sorting method is easy but slower.
* Optimized method is best → single pass.

---

