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

> 

## Highlights
The user successfully identified the sub-optimality of a stack-based approach in terms of space complexity and transitioned to the optimal in-place iterative solution. The use of three distinct pointers (`prev`, `curr`, `nextTemp`) is precisely executed to manage link redirection without data loss or redundant operations.

##Common mistakes:


## Alternative Approaches
### Approach 1
O(N) Time/O(N) Space via Recursive Approach (implicit call stack)