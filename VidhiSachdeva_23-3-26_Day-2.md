                                                             Two Sum
This solution uses a **HashMap (complement pattern)** to find two numbers whose sum equals the target 
in **O(n) time**. We iterate through the array once. For each element `nums[i]`, we calculate
its complement as `target - nums[i]`. We then check whether this complement already exists in the HashMap. If it exists,
we immediately return the stored index of the complement and the current index `i`. If not, we store the current number along 
with its index in the map. This ensures each element is processed only once, achieving optimal time complexity while using extra
space to store previously seen values.

CODE:
import java.util.*;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        
        HashMap<Integer, Integer> map = new HashMap<>();
        
        for(int i = 0; i < nums.length; i++){
            
            int complement = target - nums[i];
            
            if(map.containsKey(complement)){
                return new int[]{ map.get(complement), i };
            }
            
            map.put(nums[i], i);
        }
        
        return new int[]{-1, -1};
    }
}
