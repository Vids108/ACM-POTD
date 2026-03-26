                                                                           Move Zeroes

 The Move Zeroes problem asks to shift all zero values in an array to the end while keeping the order of non-zero elements unchanged. 
 A commonly accepted Java solution uses the two-pointer technique. One pointer scans the array from left to right, and another pointer tracks 
 the index where the next non-zero element should be placed. When a non-zero element is found, it is swapped with the element at the tracked index, 
 and the index is incremented. This ensures all non-zero elements stay in order. The algorithm runs in linear time O(n), uses constant extra space O(1), 
\and performs the modification directly in-place.

 CODE:

 class Solution {
    public void moveZeroes(int[] nums) {
        int j = 0; // position for next non-zero
        
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                int temp = nums[j];
                nums[j] = nums[i];
                nums[i] = temp;
                j++;
            }
        }
    }
}

                                
                                
