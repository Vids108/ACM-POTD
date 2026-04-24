House Robber
This problem focuses on maximizing the amount of money that can be robbed from a row of houses without robbing two adjacent houses. 
The solution uses dynamic programming to decide at each step whether to rob the current house or skip it. If the current house is robbed,
its value is added to the maximum value from two houses before. If skipped, the previous maximum is retained. To optimize space, only two 
variables are used to track these values instead of an array. The algorithm iterates through the list once, achieving O(n) time complexity 
and O(1) space complexity efficiently.

CODE:
class Solution {
    public int rob(int[] nums) {
        int prev2 = 0; 
        int prev1 = 0; 

        for (int num : nums) {
            int curr = Math.max(prev1, prev2 + num);
            prev2 = prev1;
            prev1 = curr;
        }

        return prev1;
    }
}
