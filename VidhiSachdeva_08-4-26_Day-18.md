                   Remove All Adjacent Duplicates In String
This problem requires removing all adjacent duplicate characters from a string repeatedly until no 
duplicates remain. The optimal approach uses a stack-like structure, which can be efficiently implemented
using a StringBuilder in Java. As we iterate through each character, we compare it with the last character
in the result. If they match, we remove the last character, effectively eliminating the duplicate pair. Otherwise, 
we append the current character. This process naturally handles cascading removals as new duplicates form after deletions.
The algorithm runs in O(n) time, as each character is processed once, and uses O(n) space for storing the result efficiently.

CODE:
class Solution {
    public String removeDuplicates(String s) {
        StringBuilder sb = new StringBuilder();

        for (char c : s.toCharArray()) {
            int len = sb.length();
            
            if (len > 0 && sb.charAt(len - 1) == c) {
                sb.deleteCharAt(len - 1); 
            } else {
                sb.append(c);
            }
        }

        return sb.toString();
    }
}
