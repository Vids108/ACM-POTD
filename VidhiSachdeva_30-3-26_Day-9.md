                                                           Linked List Cycle
This problem checks whether a linked list contains a cycle. A cycle occurs when a node’s next pointer
points to a previous node instead of null. The optimal solution uses Floyd’s Cycle Detection algorithm, 
also known as the Tortoise and Hare approach. Two pointers traverse the list at different speeds: a slow 
pointer moves one step at a time, while a fast pointer moves two steps. If a cycle exists, the fast pointer
will eventually meet the slow pointer. If the fast pointer reaches null, the list has no cycle. This approach runs
in O(n) time and uses O(1) space efficiently.

CODE:

public class ListNode {
    int val;
    ListNode next;

    ListNode(int val) {
        this.val = val;
        this.next = null;
    }
}

public class Solution {
    public boolean hasCycle(ListNode head) {
        if (head == null || head.next == null) {
            return false;
        }

        ListNode slow = head;
        ListNode fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;          
            fast = fast.next.next;     
            if (slow == fast) {
                return true;           
            }
        }

        return false; 
    }
}
