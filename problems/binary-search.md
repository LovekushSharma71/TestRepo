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
The implementation correctly utilizes the (left + (right - left) / 2) midpoint calculation to prevent integer overflow and correctly implements the search space reduction logic.

### Common Mistakes
_Code is structurally sound. No common mistakes flagged._

---

## 🔭 Horizon Expansion

### 🛠️ Micro-Improvement (Syntax & Execution)
In languages without automatic integer overflow like JavaScript, (left + right) >>> 1 is a more idiomatic and slightly faster bitwise alternative to Math.floor(left + (right - left) / 2).

### 🏗️ Macro-Alternative (Architectural Trade-off)
An alternative approach is to use the recursive divide-and-conquer variant of binary search, which provides O(log n) time complexity but incurs O(log n) auxiliary space complexity due to the call stack.

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
