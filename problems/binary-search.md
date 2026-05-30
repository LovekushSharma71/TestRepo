# binary-search

## 📊 Core Metrics
| Metric | Data |
| :--- | :--- |
| **Difficulty** | EASY |
| **Pattern** | None Detected |
| **Elegance Score** | `+0.8` / `+1.0` |

### ⏳ Performance vs. Optimal
- **Time Complexity:** `O(log n)` *(Optimal: `O(log n)`)*
- **Space Complexity:** `O(1)` *(Optimal: `O(1)`)*

---

## 📝 Code Review

### Approach Critique
> The logic is sound and adheres to the O(log n) requirement. Avoiding potential integer overflow by using (right - left) / 2 is an industry-standard practice, though less relevant in JavaScript due to 64-bit float representation of numbers.

### Highlights
Proper boundary management in the while loop condition (left <= right) and correct pointer manipulation prevent infinite loops and ensure every element is checked.

### Common Mistakes
_Code is structurally sound. No common mistakes flagged._

---

## 🔭 Horizon Expansion

### 🛠️ Micro-Improvement (Syntax & Execution)
Use bitwise right shift (mid = left + ((right - left) >> 1)) to perform integer division if the environment supports it, slightly increasing performance by bypassing Math.floor.

### 🏗️ Macro-Alternative (Architectural Trade-off)
Consider an Interpolation Search approach, which can perform in O(log log n) time on uniformly distributed data by estimating the probe position based on the value's magnitude.

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
