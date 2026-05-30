# container-with-most-water

## 📊 Core Metrics
| Metric | Data |
| :--- | :--- |
| **Difficulty** | MEDIUM |
| **Pattern** | None Detected |
| **Elegance Score** | `+0.5` / `+1.0` |

### ⏳ Performance vs. Optimal
- **Time Complexity:** `O(N)` *(Optimal: `O(N)`)*
- **Space Complexity:** `O(1)` *(Optimal: `O(1)`)*

---

## 📝 Code Review

### Approach Critique
> No architectural critiques apply.

### Highlights
The implementation correctly identifies the greedy property that moving the pointer pointing to the shorter line is the only way to potentially find a larger area, as the width is strictly decreasing.

### Common Mistakes
_Code is structurally sound. No common mistakes flagged._

---

## 🔭 Horizon Expansion

### 🛠️ Micro-Improvement (Syntax & Execution)
Use bitwise shifts for the width calculation if performance in extremely tight loops is required, though standard subtraction is typically optimized by V8.

### 🏗️ Macro-Alternative (Architectural Trade-off)
No macro-alternative offers superior time or space efficiency for this problem constraints.

---

## 💻 Submitted Code
```typescript
function maxArea(height: number[]): number {
    let left = 0;
    let right = height.length - 1;
    let maxWater = 0;

    while (left < right) {
        // Calculate current area
        const width = right - left;
        const currentHeight = Math.min(height[left], height[right]);
        const currentArea = width * currentHeight;
        
        maxWater = Math.max(maxWater, currentArea);

        // Move the pointer pointing to the shorter line
        if (height[left] < height[right]) {
            left++;
        } else {
            right--;
        }
    }

    return maxWater;
}
```
