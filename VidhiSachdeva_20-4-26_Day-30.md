Power of Two
This solution uses a bit manipulation trick. A power of two in binary has exactly one ‘1’ bit (e.g., 1 = 0001, 2 = 0010, 4 = 0100). 
Subtracting 1 from such a number flips all bits after that single ‘1’, turning it into a number with all lower bits set (e.g., 4 → 3 = 0011). 
Performing n & (n - 1) removes the lowest set bit. For powers of two, this results in 0.
We also check n > 0 because negative numbers and zero are not powers of two. This approach runs in constant time with no loops or recursion.

CODE:
class Solution {
    public boolean isPowerOfTwo(int n) {
        if (n <= 0) return false;
        return (n & (n - 1)) == 0;
    }
}
