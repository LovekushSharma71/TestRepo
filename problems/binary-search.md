# binary-search

## 📊 Core Metrics
| Metric | Data |
| :--- | :--- |
| **Difficulty** | EASY |
| **Pattern** | None Detected |
| **Elegance Score** | `+0.5` / `+1.0` |

### ⏳ Performance vs. Optimal
- **Time Complexity:** `O(log n)` *(Optimal: `O(log n)`)*
- **Space Complexity:** `O(1)` *(Optimal: `O(1)`)*

---

## 📝 Code Review

### Approach Critique
> The implementation is correct and follows standard conventions. No flaws detected.

### Highlights
The use of 'left + (right - left) / 2' correctly demonstrates awareness of integer overflow issues present in statically-typed languages, despite TypeScript's numeric representation.

### Common Mistakes
_Code is structurally sound. No common mistakes flagged._

---

## 🔭 Horizon Expansion

### 🛠️ Micro-Improvement (Syntax & Execution)
The 'Math.floor' could be replaced with the bitwise OR operator '((right - left) >> 1)' for a minor micro-optimization in some JavaScript engines.

### 🏗️ Macro-Alternative (Architectural Trade-off)
The problem can be solved using an iterative approach or a tail-recursive function, though recursion would consume O(log N) space on the stack.

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
