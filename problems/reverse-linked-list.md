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

> The user correctly identified the standard iterative approach for reversing a linked list. The use of `prev`, `curr`, and `nextTemp` is textbook. The reflection shows a good understanding of space complexity trade-offs.

  ## Highlights
  The code demonstrates a clear and efficient iterative reversal of the linked list using a constant amount of extra space. The pointer manipulation is accurate and effective.
  
  ## Common Mistakes
No common mistakes identified for this approach.
  ## Alternative Approaches
No alternative approaches suggested.