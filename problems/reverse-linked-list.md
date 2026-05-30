# subarray-sum-equals-k

## 📊 Core Metrics
| Metric | Data |
| :--- | :--- |
| **Difficulty** | MEDIUM |
| **Pattern** | Prefix Sum + Hash Map (Subarray Targeting) |
| **Elegance Score** | `+1.0` / `+1.0` |

### ⏳ Performance vs. Optimal
- **Time Complexity:** `O(N)` *(Optimal: `O(N)`)*
- **Space Complexity:** `O(N)` *(Optimal: `O(N)`)*

---

## 📝 Code Review

### Approach Critique
> The user correctly identified the failure of the sliding window technique due to negative numbers and implemented the optimal Hash Map-based prefix sum approach. The logic is sound, handles edge cases via the base case initialization (0: 1), and adheres to standard time and space complexities.

### Highlights
The implementation of the prefix sum difference tracking is idiomatic and clean. Using a hash map to store frequencies of prefix sums allows for O(1) lookups, ensuring O(N) total execution time.

### Common Mistakes
_Code is structurally sound. No common mistakes flagged._

---

## 🔭 Horizon Expansion

### 🛠️ Micro-Improvement (Syntax & Execution)
The code is optimal; micro-improvements would only involve minor syntactic changes like using 'Map.get' and 'Map.set' more concisely, though the current implementation is already clear.

### 🏗️ Macro-Alternative (Architectural Trade-off)
Trading O(N) space for O(N^2) time by using nested loops to calculate subarray sums, which would be necessary only if space constraints were extremely restrictive and memory was non-existent.

---

## 💻 Submitted Code
```typescript
function subarraySum(nums: number[], k: number): number {
    let count = 0;
    let sum = 0;
    const prefixMap = new Map<number, number>();
    
    // Base case: a prefix sum of 0 has occurred 1 time
    prefixMap.set(0, 1);

    for (let num of nums) {
        sum += num;
        
        // If (sum - k) exists in the map, we found valid subarrays
        if (prefixMap.has(sum - k)) {
            count += prefixMap.get(sum - k)!;
        }
        
        // Add current prefix sum to the map
        prefixMap.set(sum, (prefixMap.get(sum) || 0) + 1);
    }

    return count;
}
```
