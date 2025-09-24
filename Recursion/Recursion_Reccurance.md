
# Recursion Tree Method

The **Recursion Tree Method** is a visual approach to analyze the **time complexity** of recursive algorithms.

---

## Example 1: Factorial Calculation
**Recurrence Relation:**  
\[
T(n) = 2T(n-1) + C, \quad T(1) = C
\]

**Recursion Tree:**
```

Level 0:            C
/  &#x20;
Level 1:      T(n-1)  T(n-1)
/   \      /  &#x20;
Level 2:  T(n-2) ...  T(n-2) ...
...
Level k:  T(1) ...

```

**Cost at Each Level:**  
- Level 0: C  
- Level 1: 2C  
- Level 2: 4C  
- …  
- Level k: 2^k * C  

**Total Levels:** n (problem size reduces by 1 each level)  
**Total Cost:** C + 2C + 4C + … + 2^(n-1) * C = C(2^n - 1)  

**Time Complexity:** Θ(2^n)

---

## Example 2: Single Recursive Call
**Recurrence Relation:**  
\[
T(n) = T(n/2) + C, \quad T(1) = C
\]

**Recursion Tree:**
```

Level 0: C
Level 1: C
Level 2: C
...
Level k: C

```

**Cost at Each Level:** C  
**Total Levels:** log₂ n (problem size halves each level)  
**Total Cost:** C × log₂ n  

**Time Complexity:** Θ(log n)

---

## Example 3: Two Recursive Calls
**Recurrence Relation:**  
\[
T(n) = 2T(n/2) + C, \quad T(1) = C
\]

**Recursion Tree:**
```

Level 0:            C
/  &#x20;
Level 1:      T(n/2)  T(n/2)
/   \      /  &#x20;
Level 2:  T(n/4) ...  T(n/4) ...
...
Level k:  T(1) ...

```

**Cost at Each Level:**  
- Level 0: C  
- Level 1: 2C  
- Level 2: 4C  
- …  
- Level k: 2^k * C  

**Total Levels:** log₂ n  
**Total Cost:** C + 2C + 4C + … + 2^(log₂ n) * C = C(n - 1)  

**Time Complexity:** Θ(n)

---

## Conclusion
- **Factorial Calculation:** Θ(2^n)  
- **Single Recursive Call:** Θ(log n)  
- **Two Recursive Calls:** Θ(n)  

The recursion tree method helps **visualize recursion** and understand **time complexity** effectively.

