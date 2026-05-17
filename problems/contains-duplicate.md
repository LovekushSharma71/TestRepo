# contains-duplicate

  ## Code
  ```
  function containsDuplicate(nums) {
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] === nums[j]) {
                return true;
            }
        }
    }
    return false;
}
  ```
  
  ### Complexity Analysis
- **Time Complexity:** `O(n^2)` *(Optimal: `O(n)`)*
- **Space Complexity:** `O(1)` *(Optimal: `O(n)`)*

> The implementation uses a brute-force nested loop structure. This approach fails to scale for larger datasets due to its inherent O(n^2) time complexity, directly leading to Time Limit Exceeded errors as indicated by the user's own reflection. No optimization for checking element existence is present.

  ## Highlights
  
  
  ## Common Mistakes
- Nested loops for pairwise comparison result in quadratic time complexity, insufficient for large inputs.
  ## Alternative Approaches
### Approach 1
O(n) Time/O(n) Space using a Hash Set (add elements and check for existence).
### Approach 2
O(n log n) Time/O(1) or O(n) Space (depending on sort implementation) by sorting the array and checking adjacent elements.