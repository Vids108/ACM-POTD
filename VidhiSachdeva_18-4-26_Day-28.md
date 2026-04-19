                                                      Subtree of Another Tree
    This problem determines whether one binary tree is a subtree of another. The solution uses depth-first search to 
    traverse the main tree. At each node, it checks if the subtree rooted at that node is identical to the given subRoot 
    using a helper function. The helper function compares both trees recursively by checking node values and ensuring both 
    left and right subtrees match. If a match is found at any node, the function returns true. Otherwise, the search continues 
    in the left and right subtrees. This approach runs in O(m × n) time in the worst case and uses recursion for traversal efficiently.

    CODE:
    class Solution {
    public boolean isSubtree(TreeNode root, TreeNode subRoot) {
        if (root == null) return false;

        if (isSame(root, subRoot)) return true;

        return isSubtree(root.left, subRoot) || 
               isSubtree(root.right, subRoot);
    }

    private boolean isSame(TreeNode a, TreeNode b) {
        if (a == null && b == null) return true;
        if (a == null || b == null) return false;

        if (a.val != b.val) return false;

        return isSame(a.left, b.left) && isSame(a.right, b.right);
    }
}
