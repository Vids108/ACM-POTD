Fibonacci Number
This problem requires computing the nth Fibonacci number, where each number is the sum of the two preceding ones. 
The optimal approach uses an iterative method instead of recursion to avoid redundant computations. Two variables 
are maintained to store the previous two Fibonacci values. Starting from the base cases, the loop updates these values
until reaching the nth position. This approach eliminates the overhead of recursive calls and ensures efficient computation.
The algorithm runs in O(n) time and uses O(1) space, making it highly efficient. It is preferred over recursive solutions,
which have exponential time complexity without memoization.

CODE:
class Solution {
    public int fib(int n) {
        if (n <= 1) return n;

        int prev1 = 0, prev2 = 1;

        for (int i = 2; i <= n; i++) {
            int curr = prev1 + prev2;
            prev1 = prev2;
            prev2 = curr;
        }

        return prev2;
    }
}
