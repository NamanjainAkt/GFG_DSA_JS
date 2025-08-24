# Iterative Binary Exponentiation

## Overview
Compute `x` raised to the power `y` (xʸ) with optimal time and space complexity.

## Requirements
- **Time Complexity**: O(log y)
- **Space Complexity**: O(1)

## Examples
- `x = 3, y = 5` → 243
- `x = 2, y = 5` → 32

## Implementation

### Iterative Binary Exponentiation (Recommended)
```javascript
function power(x, y) {
  let result = 1;
  
  while (y > 0) {
    // If current bit is set, multiply result by x
    if (y & 1) {
      result *= x;
    }
    
    // Square x to get next power of 2
    x *= x;
    
    // Right shift y (divide by 2)
    y = y >> 1;
  }
  
  return result;
}
```
#### Complexity:

- Time: O(log y) - Number of bits in y

- Space: O(1) - Constant extra space

### How It Works
#### The algorithm uses binary exponentiation:

1. Binary representation: Express y as sum of powers of 2

2. Bit checking: For each set bit in y, multiply result by corresponding power of x

3. Power doubling: Square x at each step (x¹, x², x⁴, x⁸, ...)

4. Bit shifting: Process each bit of y from LSB to MSB

### Example: 3⁵ (y = 5 = 101 in binary)
- Step 1: y=5 (101), LSB=1 → result = 1 × 3 = 3, x = 3² = 9, y = 2

- Step 2: y=2 (10), LSB=0 → result = 3, x = 9² = 81, y = 1

- Step 3: y=1 (1), LSB=1 → result = 3 × 81 = 243, x = 81², y = 0

### Why Iterative Over Recursive?
- No stack overhead: O(1) space vs O(log y) for recursive

- Better performance: No function call overhead

- Same time complexity: Both are O(log y)

### Key Features
- Efficient: Processes each bit exactly once

- General: Works for any integer y ≥ 0

- Optimal: Meets both time and space constraints

### Usage
```javascript
console.log(power(3, 5));  // 243
console.log(power(2, 5));  // 32
console.log(power(5, 3));  // 125
```