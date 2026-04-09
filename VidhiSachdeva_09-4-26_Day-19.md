                                        Backspace String Compare
This problem compares two strings after simulating backspace operations represented by the '#' character. 
The optimal solution avoids building new strings and instead uses two pointers starting from the end of each 
string. A counter tracks how many characters to skip when a backspace is encountered. As the pointers move backward, 
characters are skipped accordingly until a valid character is found. The valid characters from both strings are then 
compared. If they differ, the result is false. If traversal completes without mismatches, the strings are equal. This 
approach runs in O(n) time and uses O(1) space efficiently without extra data structures.

CODE:
class Solution {
    public boolean backspaceCompare(String s, String t) {
        int i = s.length() - 1;
        int j = t.length() - 1;

        int skipS = 0, skipT = 0;

        while (i >= 0 || j >= 0) {

            // process s
            while (i >= 0) {
                if (s.charAt(i) == '#') {
                    skipS++;
                    i--;
                } else if (skipS > 0) {
                    skipS--;
                    i--;
                } else break;
            }
            while (j >= 0) {
                if (t.charAt(j) == '#') {
                    skipT++;
                    j--;
                } else if (skipT > 0) {
                    skipT--;
                    j--;
                } else break;
            }
            if (i >= 0 && j >= 0) {
                if (s.charAt(i) != t.charAt(j)) return false;
            } else {
                if (i >= 0 || j >= 0) return false;
            }

            i--;
            j--;
        }

        return true;
    }
}
