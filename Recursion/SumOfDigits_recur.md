
# Sum of Digits Using Recursion

Given a non-negative integer `n`, calculate the **sum of its digits** recursively.

---

## Examples

| Input  | Output | Explanation       |
|--------|--------|-----------------|
| 253    | 10     | 2 + 5 + 3 = 10  |
| 9987   | 33     | 9 + 9 + 8 + 7 = 33 |
| 10     | 1      | 1 + 0 = 1       |

---

## Recursive Thinking

- Split `n` into **last digit** and **remaining number**:

```text
lastDigit = n % 10         // rightmost digit
remaining = Math.floor(n/10) // remaining number
````

* Recurrence relation:

$$
getSum(n) = getSum(remaining) + lastDigit
$$

---

### Recursion Tree Example (n = 253)

```
getSum(253)
→ getSum(25) + 3
    → getSum(2) + 5
        → getSum(0) + 2
            → returns 0
Sum returns back up:
getSum(2) = 2
getSum(25) = 7
getSum(253) = 10
```

---

## Recursive Implementation

```js
function getSum(n) {
    if (n <= 9) return n;         // Base case: single-digit number

    const lastDigit = n % 10;     // Extract last digit
    const remaining = Math.floor(n / 10); // Remaining digits

    return getSum(remaining) + lastDigit; // Recursive call
}

// Example usage
const num = 253;
console.log(`Sum of digits of ${num} is:`, getSum(num)); // Output: 10
```

**Output:**

```
Sum of digits of 253 is: 10
```

---

## Complexity

* **Time Complexity:** Θ(D), where D = number of digits in `n`
* **Space Complexity:** Θ(D) due to recursion stack

**Note:**

* Iterative solution can reduce space to Θ(1) using a loop:

```js
let sum = 0;
let n = 253;
while(n > 0) {
    sum += n % 10;
    n = Math.floor(n / 10);
}
console.log(sum); // 10
```

* Use iterative version when recursion stack size is a concern.
