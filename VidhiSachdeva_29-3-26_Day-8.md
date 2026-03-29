                                                    Reverse Linked List

  Reversing a singly linked list means changing the direction of its pointers so the last node becomes the head.
  Iterate through the list while maintaining three references: previous, current, and next. Initially, previous is
  null and current is head. At each step, store next as current.next, redirect current.next to previous, then move
  previous to current and current to next. Continue until current becomes null. Finally, previous points to the new head of the reversed list. 
  This in-place approach runs in O(n) time with O(1) space and is the standard accepted solution on LeetCode. It avoids recursion and memory overhead.

  CODE:
class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode curr = head;
        
        while (curr != null) {
            ListNode nextTemp = curr.next; 
            curr.next = prev;             
            prev = curr;                  
            curr = nextTemp;               
        }
        
        return prev; // new head
    }
}
