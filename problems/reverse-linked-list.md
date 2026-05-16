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

> Their initial consideration of using an auxiliary data structure like an array or stack, while functional, would have introduced O(N) space complexity, violating the principle of an in-place linked list manipulation. The final provided code, however, does not suffer from this flaw.

## Highlights
Successfully identified and implemented the iterative three-pointer technique for in-place reversal, achieving optimal O(1) space complexity. The pointer management is clear and efficient.

##Common mistakes:


## Alternative Approaches
### Approach 1
Recursive solution: Achieves O(N) time but utilizes O(N) space due to recursion stack depth. While functionally equivalent, it sacrifices space optimality for a potentially more concise implementation.