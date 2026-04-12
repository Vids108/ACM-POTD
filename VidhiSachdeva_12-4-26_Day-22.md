Flood Fill
This problem involves recoloring a region in a 2D image starting from a given pixel. The goal is to change the 
color of the starting pixel and all connected pixels that share the same original color. The solution uses Depth
First Search (DFS) to explore all valid neighboring cells recursively. First, the original color is stored, and if 
it matches the new color, no changes are needed. Otherwise, DFS is applied to each cell, ensuring it stays within
bounds and matches the original color before updating it. The algorithm runs in O(m × n) time and uses recursion 
stack space for traversal efficiently.

CODE:
class Solution {
    public int[][] floodFill(int[][] image, int sr, int sc, int color) {
        int original = image[sr][sc];

        if (original == color) return image;

        dfs(image, sr, sc, original, color);
        return image;
    }

    private void dfs(int[][] image, int r, int c, int original, int color) {
        if (r < 0 || c < 0 || r >= image.length || c >= image[0].length
                || image[r][c] != original) {
            return;
        }

        image[r][c] = color;
        dfs(image, r + 1, c, original, color);
        dfs(image, r - 1, c, original, color);
        dfs(image, r, c + 1, original, color);
        dfs(image, r, c - 1, original, color);
    }
}
