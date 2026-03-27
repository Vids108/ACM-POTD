                                               Check if N and Its Double Exist

  The solution uses a HashSet to efficiently track numbers encountered while iterating through the array.
  For each element, it checks whether its double already exists in the set, which would satisfy the condition. 
  Additionally, if the current number is even, it checks whether its half is present. This ensures both 
  possible relationships (double and half) are covered. If either condition is true, the function immediately returns true.
  Otherwise, the number is added to the set for future checks.
  This approach avoids nested loops and reduces time complexity to O(n) with O(n) extra space.

  CODE:

import java.util.HashSet;

class Solution {
    public boolean checkIfExist(int[] arr) {
        HashSet<Integer> seen = new HashSet<>();
        
        for (int num : arr) {
            if (seen.contains(2 * num)) {
                return true;
            }
            if (num % 2 == 0 && seen.contains(num / 2)) {
                return true;
            }
            
            seen.add(num);
        }
        
        return false;
    }
}

  
                                                  
