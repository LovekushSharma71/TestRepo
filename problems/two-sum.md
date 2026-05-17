# two-sum

  ## Code
  ```
  function twoSum(nums, target) {
    const map = new Map();
    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];
        if (map.has(complement)) {
            return [map.get(complement), i];
        }
        map.set(nums[i], i);
    }
    return [];
}
  ```
  
  ### Complexity Analysis
- **Time Complexity:** `O(N)` *(Optimal: `O(N)`)*
- **Space Complexity:** `O(N)` *(Optimal: `O(N)`)*

> The implementation is fully optimal. No architectural critiques apply.

  ## Highlights
  The single-pass approach utilizing a hash map to store complements is efficient and directly addresses the problem's constraints.
  
  ## Common Mistakes
No common mistakes identified for this approach.
  ## Alternative Approaches
No alternative approaches suggested.