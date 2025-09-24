
# 📌 Arrays – Advanced Understanding

### ⚡ Memory Model

* **C/C++**: Arrays store **actual data** in contiguous memory.
* **JS/Python**: Arrays store **references (pointers)** contiguously.

  * Each reference is of equal size → can be stored contiguously.
  * Actual data (number, string, object, etc.) may be elsewhere in memory.
  * This is why JS arrays can hold **heterogeneous data types**.

---

## ✅ Advantages of Arrays

1. **Random Access (O(1))**

   * Direct formula for element address:

     ```
     base_address + (i * size_of_each_item)
     ```
   * Very fast element access using index.

2. **Cache Friendly**

   * Elements/references are contiguous → CPU prefetch improves speed.

---

## ❌ Disadvantages of Arrays

1. **Insertion/Deletion (O(n))**

   * Adding/removing at start/middle requires shifting.
   * Example:

     ```js
     arr.unshift(10); // O(n)
     arr.shift();     // O(n)
     ```
   * Only `push()` and `pop()` at end are O(1) average.

2. **Search in Unsorted Array = O(n)**

   * Requires linear scan.
   * If sorted → **Binary Search O(log n)**.
   * For faster lookups → use **Hash Tables (Objects/Maps in JS)**.

---

## ⚡ Dynamic Nature of JS Arrays

* **Grow/shrink automatically**.
* When exceeding capacity:

  1. Allocate a **bigger block** (often ×2).
  2. Copy old items into new block.
  3. Insert new item.

📖 Example:
Initial size = 10 → insert 11th → resize to 20 → copy → insert.

---

## ⏱ Time Complexity of Common Operations

| Operation                     | Time Complexity | Notes              |
| ----------------------------- | --------------- | ------------------ |
| **Access by index**           | O(1)            | Direct calculation |
| **Push (end insert)**         | O(1) *avg*      | O(n) when resizing |
| **Pop (end remove)**          | O(1)            | No shifting        |
| **Unshift (insert at start)** | O(n)            | All elements shift |
| **Shift (remove at start)**   | O(n)            | All elements shift |
| **Search (unsorted)**         | O(n)            | Linear scan        |
| **Search (sorted)**           | O(log n)        | Binary search      |

👉 **Why `push()` is still O(1) avg?**

* N pushes = O(N).
* 1 resize = O(N) copy.
* Total = O(2N) → avg per push = O(1).

---

## 🔄 Alternatives to Arrays

Depending on the use case:

* **Linked List** → Faster insertions/deletions, slower access.
* **Stack/Queue** → Specialized versions of arrays with restricted access.
* **Hash Table (Object/Map in JS)** → Faster lookups (O(1) avg).
* **Trees/Graphs** → For hierarchical or network relationships.

---

📖 **In summary:**

* Use arrays when you need **fast indexing & sequential storage**.
* Avoid them for **frequent insertions/deletions at start/middle**.
* JS arrays are flexible but internally use **reference storage + dynamic resizing**.

