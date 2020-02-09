# Remove Linked List Elements
## https://leetcode.com/problems/remove-linked-list-elements

Remove all elements from a linked list of integers that have value val.

Example:

Input:  1->2->6->3->4->5->6, val = 6
Output: 1->2->3->4->5

## Implementation :

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        ListNode current = head;
        ListNode prev = null;
        
        while(current != null)  {
            if(current.val == val){
                if(prev != null){
                    prev.next = current.next;
                } else{
                    head = current.next;
                }
            } else{
                prev = current;
            }
            
            current = current.next;    
        }  
        
        return head;
    }
}
```
