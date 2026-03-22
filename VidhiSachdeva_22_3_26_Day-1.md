                                                 REMOVE DUPLICATES FROM ARRAY
This solution removes duplicates from a sorted array using the two-pointer technique. It maintains one pointer i to track 
the position of the last unique element and another pointer j to traverse the array. Starting from index 1,
it compares each element with the element at i. If a new unique element is found, i is incremented and the element is copied to position i. 
This ensures all unique elements are placed at the beginning of the array in order. Finally, the function returns i + 1, which represents
the total number of unique elements.

CODE:
class Solution {
    public int removeDuplicates(int[] nums) {
        if (nums.length == 0) return 0;

        int i = 0;

        for (int j = 1; j < nums.length; j++) {
            if (nums[j] != nums[i]) {
                i++;
                nums[i] = nums[j];
            }
        }

        return i + 1;
    }
}
