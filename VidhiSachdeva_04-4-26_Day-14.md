Palindrome Linked List
This problem checks whether a singly linked list is a palindrome, meaning it reads the same forward and backward.
The optimal approach uses two pointers to find the middle of the list. After locating the midpoint, the second half 
of the list is reversed in place. Then, the first half and the reversed second half are compared node by node. If all 
corresponding values match, the list is a palindrome; otherwise, it is not. This method is efficient because it runs in
O(n) time and uses O(1) extra space, avoiding the need for additional data structures like arrays or stacks.

CODE:
class Solution {
    public boolean isPalindrome(ListNode head) {
        if (head == null || head.next == null) return true;

        ListNode slow = head;
        ListNode fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }

        ListNode prev = null;
        while (slow != null) {
            ListNode nextTemp = slow.next;
            slow.next = prev;
            prev = slow;
            slow = nextTemp;
        }

        ListNode first = head;
        ListNode second = prev;

        while (second != null) {
            if (first.val != second.val) return false;
            first = first.next;
            second = second.next;
        }

        return true;
    }
}
