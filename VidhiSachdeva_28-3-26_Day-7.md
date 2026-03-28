                                                           Rotate Array
This solution rotates the array to the right by k steps using an in-place reversal technique.
First, k is reduced using modulo to handle cases where k exceeds the array length. The entire array 
is reversed, placing elements in opposite order. Then, the first k elements are reversed to restore their correct rotated positions. 
Finally, the remaining elements are reversed to maintain their relative order. This approach avoids using extra space and performs 
the rotation efficiently in linear time.The reverse helper function swaps elements between two indices until they meet,
ensuring correct rearrangement of array elements.

CODE:
class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        k = k % n;  // handle k > n
        
        reverse(nums, 0, n - 1);       
        reverse(nums, 0, k - 1);       
        reverse(nums, k, n - 1);       
    }
    
    private void reverse(int[] nums, int start, int end) {
        while (start < end) {
            int temp = nums[start];
            nums[start] = nums[end];
            nums[end] = temp;
            start++;
            end--;
        }
    }
}
