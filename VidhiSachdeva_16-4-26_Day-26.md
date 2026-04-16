                           Invert Binary Tree
This problem involves inverting a binary tree by swapping the left and right children of every node.
The solution uses a depth-first traversal approach with recursion. Starting from the root, the algorithm 
swaps its left and right child nodes, then recursively applies the same process to its subtrees. This ensures
that all nodes in the tree are inverted correctly. If a node is null, it simply returns without any operation.
The algorithm visits each node exactly once, resulting in O(n) time complexity, where n is the number of nodes, 
and uses O(h) space due to recursion stack, where h is tree height.

CODE:
class Solution {
    public TreeNode invertTree(TreeNode root) {
        if (root == null) return null;

        TreeNode temp = root.left;
        root.left = root.right;
        root.right = temp;
        invertTree(root.left);
        invertTree(root.right);

        return root;
    }
}
