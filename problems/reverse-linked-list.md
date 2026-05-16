# reverse-linked-list

## Code
```
function reverseList(head) {
    let prev = null;
    let curr = head;
        while (curr != null) {
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


##Common mistakes:
undefined

## Alternative Approaches
