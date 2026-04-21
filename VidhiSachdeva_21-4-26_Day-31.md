Climbing Stairs
This problem follows a Fibonacci-like pattern. To reach step n, you can come either from step n-1 (one step) or n-2 (two steps). 
So the recurrence is f(n) = f(n-1) + f(n-2). Instead of using recursion, which is slow due to repeated calculations, we use an 
iterative dynamic programming approach. We store only the last two computed values (prev1 and prev2) to optimize space. Starting 
from base cases f(1)=1 and f(2)=2, we build up to n. This gives an O(n) time complexity and O(1) space complexity, making it efficient.
CODE:

class Solution {
    public int climbStairs(int n) {
        if (n <= 2) return n;
        
        int prev1 = 1, prev2 = 2;
        
        for (int i = 3; i <= n; i++) {
            int curr = prev1 + prev2;
            prev1 = prev2;
            prev2 = curr;
        }
        
        return prev2;
    }
}
