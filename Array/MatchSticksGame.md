
# Matchsticks Game

Two friends, **A** and **B**, are playing the game of matchsticks.  

- A group of `N` matchsticks is placed on the table.  
- Players can pick **1 to 4** matchsticks on their turn.  
- The player who picks the **last matchstick wins**.  
- **A starts first**. Determine how many matchsticks A should pick on the first turn to guarantee a win.  
- If it is impossible for A to guarantee a win, return `-1`.

---

## Examples

**Example 1:**  

**Input:**  
`N = 48`  

**Output:**  
`3`  

**Explanation:**  
- Player A can guarantee a win by picking 3 matchsticks on the first turn.  

---

**Example 2:**  

**Input:**  
`N = 15`  

**Output:**  
`-1`  

**Explanation:**  
- No matter how many matchsticks A picks first, B can always win if both play optimally.  

---

## Constraints

- `1 <= N <= 10^18`  
- Both players play optimally.

---

## Approach

- The game is a **classic Nim variant**.  
- When `N % 5 == 0`, the first player **cannot guarantee a win**.  
- Otherwise, the first player should pick `N % 5` matchsticks to leave a multiple of 5 for the second player.

---

## JavaScript Implementation

```javascript
// User function Template for javascript

/**
 * @param {BigInt} n
 * @return {number}
 */
class Solution {
    matchGame(n) {
        let res = n % 5n;       // modulo 5 with BigInt
        return res === 0n ? -1 : Number(res);
    }
}

// Test Cases
let obj = new Solution();
console.log(obj.matchGame(48n)); // 3
console.log(obj.matchGame(15n)); // -1
````

**Time Complexity:** O(1)
**Space Complexity:** O(1)
