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

> The user correctly identified the inefficiency of the O(N) space approach. The current iterative solution is optimal in terms of time and space complexity. The pointer manipulation is standard for this problem.

  ## Highlights
  The user's explanation of using three pointers (`prev`, `curr`, `nextTemp`) demonstrates a solid understanding of how to reverse a linked list iteratively in-place.
  
  ## Common Mistakes
No common mistakes identified for this approach.
  ## Alternative Approaches
No alternative approaches suggested.