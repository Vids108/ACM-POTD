                                              Middle of the Linked List
             This problem requires finding the middle node of a singly linked list. The optimal approach uses two pointers: slow and fast.
             The slow pointer advances one step at a time, while the fast pointer advances two steps. When the fast pointer reaches the end
             of the list, the slow pointer will be positioned at the middle node. If the list has an even number of nodes, the algorithm returns 
             the second middle node as required. This technique is efficient because it traverses the list only once, resulting in O(n) time complexity
             and O(1) space complexity without using extra data structures or modifying the list.

             CODE:

        class Solution {
        public ListNode middleNode(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;          
            fast = fast.next.next;     
        }

        return slow;
    }
}
