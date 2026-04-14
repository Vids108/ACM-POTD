Find Center of Star Graph
This problem involves identifying the center of a star graph, where one 
central node is connected to all other nodes. Since the graph has n nodes
and n−1 edges, the center node must appear in every edge. The key observation 
is that the center will be common in any two edges. Therefore, we only need to 
compare the first two edges to find the common node. If one endpoint of the first
edge matches any endpoint of the second edge, that node is the center. This approach runs in
constant time O(1) and requires no extra space, making it extremely efficient.

CODE:
class Solution {
    public int findCenter(int[][] edges) {
        if (edges[0][0] == edges[1][0] || edges[0][0] == edges[1][1]) {
            return edges[0][0];
        }
        return edges[0][1];
    }
}
