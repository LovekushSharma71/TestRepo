# binary-search

## 📊 Core Metrics
| Metric | Data |
| :--- | :--- |
| **Difficulty** | EASY |
| **Pattern** | Standard Binary Search (Target Lookup) |
| **Elegance Score** | `+1.0` / `+1.0` |

### ⏳ Performance vs. Optimal
- **Time Complexity:** `O(log n)` *(Optimal: `O(log n)`)*
- **Space Complexity:** `O(1)` *(Optimal: `O(1)`)*

---

## 📝 Code Review

### Approach Critique
> No architectural critiques apply.

### Highlights
The implementation correctly utilizes the (left + (right - left) / 2) midpoint calculation to prevent potential integer overflow, which is standard professional practice.

### Common Mistakes
_Code is structurally sound. No common mistakes flagged._

---

## 🔭 Horizon Expansion

### 🛠️ Micro-Improvement (Syntax & Execution)
While Math.floor is correct in JS, bitwise shift (left + (right - left) >>> 1) is a common micro-optimization for performance in some engines.

### 🏗️ Macro-Alternative (Architectural Trade-off)
Consider implementing an iterative approach vs. a recursive approach; while recursion adds O(log n) stack space, it can sometimes improve readability in complex variants like searching on rotated or matrix-based structures.

---

## 💻 Submitted Code
```typescript
function search(nums: number[], target: number): number {
    let left = 0;
    let right = nums.length - 1;

    while (left <= right) {
        // Using (right - left) / 2 to prevent potential overflow in larger languages
        const mid = Math.floor(left + (right - left) / 2);
        
        if (nums[mid] === target) {
            return mid;
        } else if (nums[mid] < target) {
            left = mid + 1; // Target is in the right half
        } else {
            right = mid - 1; // Target is in the left half
        }
    }

    return -1; // Target not found
}
```
