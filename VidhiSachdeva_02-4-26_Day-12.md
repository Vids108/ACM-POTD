                                      Remove Duplicates from Sorted List
This problem involves removing duplicate values from a sorted linked list so that each element appears only once. 
Since the list is sorted, duplicates will always appear next to each other, making it easier to detect them.
The solution uses a single pointer to traverse the list. At each step, it compares the current node with the next node. 
If their values are equal, the duplicate node is skipped by adjusting the next pointer. Otherwise, the pointer moves forward.
This approach ensures that the list remains sorted and contains only unique elements. It runs in O(n) time with O(1) extra space.

CODE:
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode current = head;

        while (current != null && current.next != null) {
            if (current.val == current.next.val) {
                current.next = current.next.next; 
            } else {
                current = current.next; 
            }
        }

        return head;
    }
}
