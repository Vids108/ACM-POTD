Intersection of Two Linked Lists
This problem requires finding the node where two singly linked lists intersect. 
The optimal approach uses two pointers that traverse both lists. Each pointer starts 
at the head of one list and moves forward one step at a time. When a pointer reaches the 
end of its list, it is redirected to the head of the other list. This way, both pointers
traverse equal total lengths. If an intersection exists, they will meet at the intersection node. 
If not, both pointers will eventually reach null. This method runs in O(n + m) time and uses O(1) 
extra space, making it efficient and elegant.

CODE:
public class Solution {
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        if (headA == null || headB == null) return null;

        ListNode a = headA;
        ListNode b = headB;

        while (a != b) {
            a = (a == null) ? headB : a.next;
            b = (b == null) ? headA : b.next;
        }

        return a;
    }
}
