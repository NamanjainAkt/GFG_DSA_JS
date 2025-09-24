
# Print Numbers from 1 to N

Given a number `N`, the task is to print numbers from `1` to `N`.

---

## Examples

**Input:** N = 10  
**Output:** 1 2 3 4 5 6 7 8 9 10  

**Input:** N = 7  
**Output:** 1 2 3 4 5 6 7  

---

## Method 1: Recursive Approach

Print smaller numbers first, then the current number.

**Steps:**
1. **Base Case:** If N <= 0, return.  
2. **Recursive Step:** Call the function with `N-1` first, then print `N`.

```js
class GFG {
  printNos(n) {
    if (n > 0) {
      this.printNos(n - 1);
      console.log(n);
    }
    return;
  }
}

// Driver code
(function main() {
  const g = new GFG();
  g.printNos(10);
})();
````

**Output:**

```
1 2 3 4 5 6 7 8 9 10
```

* **Time Complexity:** O(N)
* **Auxiliary Space:** O(N) (due to recursive call stack)

---

## Method 2: Iterative Approach

Use a simple loop from 1 to N.

```js
function printIncreasingIterative(N) {
  for (let i = 1; i <= N; i++) {
    console.log(i);
  }
}

printIncreasingIterative(10);
```

**Output:**

```
1 2 3 4 5 6 7 8 9 10
```

* **Time Complexity:** O(N)
* **Auxiliary Space:** O(1)

---

## Note

1. **Recursion** helps understand **call stacks** and **base cases**.
2. **Iteration** is more **efficient** as it avoids extra memory usage.
3. In recursion, the function builds up calls from 1 to N and prints while returning.



