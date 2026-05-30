# binary-search

## 📊 Core Metrics
| Metric | Data |
| :--- | :--- |
| **Difficulty** | EASY |
| **Pattern** | None Detected |
| **Elegance Score** | `+1.0` / `+1.0` |

### ⏳ Performance vs. Optimal
- **Time Complexity:** `O(log n)` *(Optimal: `O(log n)`)*
- **Space Complexity:** `O(1)` *(Optimal: `O(1)`)*

---

## 📝 Code Review

### Approach Critique
> No architectural critiques apply.

### Highlights
The implementation correctly utilizes the binary search template with robust overflow prevention by calculating the midpoint as left + (right - left) / 2 and properly adjusting search boundaries.

### Common Mistakes
_Code is structurally sound. No common mistakes flagged._

---

## 🔭 Horizon Expansion

### 🛠️ Micro-Improvement (Syntax & Execution)
The syntax is optimal for TypeScript; no micro-improvements are necessary.

### 🏗️ Macro-Alternative (Architectural Trade-off)
For massive static datasets where performance is critical, one could consider using an interpolated search to potentially achieve O(log log n) time complexity, albeit with O(n) worst-case performance.

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
