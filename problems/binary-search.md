# binary-search

## 📊 Core Metrics
| Metric | Data |
| :--- | :--- |
| **Difficulty** | EASY |
| **Pattern** | None Detected |
| **Elegance Score** | `+1.0` / `+1.0` |

### ⏳ Performance vs. Optimal
- **Time Complexity:** `O(log N)` *(Optimal: `O(log N)`)*
- **Space Complexity:** `O(1)` *(Optimal: `O(1)`)*

---

## 📝 Code Review

### Approach Critique
> No architectural critiques apply.

### Highlights
The implementation correctly utilizes the optimal mid-calculation formula (left + (right - left) / 2) to avoid potential overflow issues, despite JavaScript's Number type being a 64-bit float. The boundary conditions (left <= right) and the pointer updates (mid + 1 / mid - 1) are strictly correct.

### Common Mistakes
_Code is structurally sound. No common mistakes flagged._

---

## 🔭 Horizon Expansion

### 🛠️ Micro-Improvement (Syntax & Execution)
Use bitwise shift (left + ((right - left) >> 1)) for marginally faster integer division in environments where Math.floor incurs overhead.

### 🏗️ Macro-Alternative (Architectural Trade-off)
Consider implementing an iterative approach using a single pointer and a range width variable, or a recursive approach if specific tail-call optimization requirements are present in the target environment.

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
