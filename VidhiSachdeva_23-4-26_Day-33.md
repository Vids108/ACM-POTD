                                              Min Cost Climbing Stairs
This problem involves finding the minimum cost required to reach the top of a staircase, where each step has an associated cost.
You can climb either one or two steps at a time. The solution uses dynamic programming to compute the minimum cost efficiently. 
At each step, the cost is calculated by adding the current step’s cost to the minimum of the costs required to reach the previous two steps.
To optimize space, only two variables are maintained instead of a full array. After processing all steps, the result is the minimum of the last
two computed values. This approach runs in O(n) time and uses O(1) space.

CODE:
class Solution {
    public int minCostClimbingStairs(int[] cost) {
        int prev2 = 0; 
        int prev1 = 0; 

        for (int i = 0; i < cost.length; i++) {
            int curr = cost[i] + Math.min(prev1, prev2);
            prev2 = prev1;
            prev1 = curr;
        }

        return Math.min(prev1, prev2);
    }
}
