
# Recursion in JavaScript

## What is Recursion?
Recursion is the process in which a function calls itself (directly or indirectly).  
It helps solve problems like **Tower of Hanoi, Tree Traversals, DFS of Graph**, etc.

---

## Types of Recursion
### 1. Direct Recursion
```js
function fun(n) {
    if (n <= 0) return;   // base case
    console.log("gfg");
    fun(n - 1);           // recursive call
}
````


### 2. Indirect Recursion

```js
function fun1() {
    fun2();
}
function fun2() {
    fun1();
}
```

---

## Base Case

The **base case** stops recursion.
Without it → Infinite recursion → **Stack Overflow**.

```js
function fact(n) {
    if (n == 0) return 1; // base case
    return n * fact(n - 1);
}
```

❌ Wrong base case example:

```js
function fact(n) {
    if (n == 100) return 1; // never reached
    return n * fact(n - 1); // stack overflow
}
```

---

## How Problems Are Solved Using Recursion

* Represent the problem in terms of **smaller subproblems**.
* Define a **base case**.

Example: Factorial
`fact(n) = n * fact(n-1)` with `fact(0) = 1`.

---

## Memory Allocation in Recursion

* Each call gets **its own local variables**.
* Calls are stored on the **call stack** (LIFO).
* Once base case is reached, functions return in reverse order.

### Example:

```js
function printFun(test) {
    if (test < 1) return;
    console.log(test);       // before recursion
    printFun(test - 1);      // recursive call
    console.log(test);       // after recursion
}

printFun(3);
```

**Output:**

```
3
2
1
1
2
3
```

---

## Advantages

* Clean & simple code for problems like:

  * Tree traversals
  * Tower of Hanoi
  * Divide-and-conquer algorithms
* Natural fit for problems with subproblems.

## Disadvantages

* Higher memory usage (stack calls).
* Slower due to function call overhead.
* Risk of **stack overflow** if base case is missing/incorrect.
