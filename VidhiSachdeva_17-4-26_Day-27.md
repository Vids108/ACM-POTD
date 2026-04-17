Diameter of Binary Tree
This problem requires finding the diameter of a binary tree, defined as the longest path between any two nodes measured in edges.
The solution uses depth-first search to compute the height of each subtree. At every node, the diameter passing through it is calculated
as the sum of the heights of its left and right subtrees. A global variable keeps track of the maximum diameter found during traversal.
The height of each node is returned to its parent to continue the calculation. This approach ensures all nodes are processed once,
resulting in O(n) time complexity and O(h) space due to recursion stack usage.

CODE:
class Solution {
    int diameter = 0;

    public int diameterOfBinaryTree(TreeNode root) {
        height(root);
        return diameter;
    }

    private int height(TreeNode node) {
        if (node == null) return 0;

        int left = height(node.left);
        int right = height(node.right);


        diameter = Math.max(diameter, left + right);

        return 1 + Math.max(left, right);
    }
}
