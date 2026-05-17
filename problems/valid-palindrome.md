# valid-palindrome

  ## Code
  ```
  def isPal(a):
   return a==a[::-1]
  ```
  
  ### Complexity Analysis
- **Time Complexity:** `O(N)` *(Optimal: `O(N)`)*
- **Space Complexity:** `O(N)` *(Optimal: `O(1)`)*

> The implementation utilizes string slicing to reverse the entire string, which is inefficient in terms of space complexity. A more optimal approach would involve two pointers to compare characters from both ends inward.

  ## Highlights
  
  
  ## Common Mistakes
- Slicing creates a new reversed string, which is not space-optimal.
  ## Alternative Approaches
### Approach 1
Consider an iterative approach using two pointers, one starting at the beginning and the other at the end of the string, moving towards the center. This achieves O(1) space complexity by avoiding the creation of a new reversed string.