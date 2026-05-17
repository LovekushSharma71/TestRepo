# reverse-linked-list

  ## Code
  ```
  function reverseList(head) {
      let prev = null;
      let curr = head;
      
      while (curr !== null) {
          let nextTemp = curr.next; // Store next node
          curr.next = prev;         // Reverse the link
           prev = curr;              // Move prev forward
           curr = nextTemp;          // Move curr forward
       }
       
       return prev;
   }
  ```
  
  ### Complexity Analysis
- **Time Complexity:** `O(N)` *(Optimal: `O(N)`)*
- **Space Complexity:** `O(1)` *(Optimal: `O(1)`)*

> The user's understanding of space complexity is sound, but their reflection incorrectly labels the pattern as 'Fast & Slow Pointers'. This iterative approach is more accurately characterized by pointer manipulation for reversal.

  ## Highlights
  The iterative approach correctly identifies the need for three pointers (`prev`, `curr`, `nextTemp`) to manage the reversal process efficiently, resulting in optimal O(N) time and O(1) space complexity.
  
  ## Common Mistakes
No common mistakes identified for this approach.
  ## Alternative Approaches
No alternative approaches suggested.