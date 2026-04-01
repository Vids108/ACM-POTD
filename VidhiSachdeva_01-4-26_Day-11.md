                                 Merge Two Sorted Lists
This problem involves merging two sorted linked lists into a single sorted list. The optimal approach uses an iterative
method with a dummy node to simplify edge cases. Two pointers traverse the input lists, comparing their current node values.
The smaller node is appended to the result list, and the corresponding pointer is advanced. This process continues until one 
list is exhausted. After that, the remaining nodes from the other list are appended directly. This algorithm runs in O(n + m) time, 
where n and m are the lengths of the lists, and uses O(1) extra space since it reuses existing nodes efficiently.

CODE:
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode dummy = new ListNode(-1);
        ListNode current = dummy;

        while (list1 != null && list2 != null) {
            if (list1.val <= list2.val) {
                current.next = list1;
                list1 = list1.next;
            } else {
                current.next = list2;
                list2 = list2.next;
            }
            current = current.next;
        }

        // attach remaining nodes
        if (list1 != null) {
            current.next = list1;
        } else {
            current.next = list2;
        }

        return dummy.next;
    }
}
