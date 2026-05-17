# valid-palindrome

  ## Code
  ```
  def isPal(a):
   return a==a[::-1]
  ```
  
  ### Complexity Analysis
- **Time Complexity:** `O(N)` *(Optimal: `O(N)`)*
- **Space Complexity:** `O(N)` *(Optimal: `O(1)`)*

> The solution is incomplete, failing to address the core preprocessing steps required by the problem statement. The `isPal` function correctly checks for palindromes on a pre-processed string, but the crucial transformation from raw input to a clean string is missing.

  ## Highlights
  
  
  ## Common Mistakes
- The provided code snippet is incomplete. It lacks the necessary logic to handle the problem statement's requirements of converting to lowercase and removing non-alphanumeric characters.
  ## Alternative Approaches
### Approach 1
Two Pointers: Iterate from both ends of the string inwards, comparing characters after ensuring they are alphanumeric and lowercased. This achieves O(N) time complexity with O(1) space complexity by avoiding the creation of a new string for the reversed version.