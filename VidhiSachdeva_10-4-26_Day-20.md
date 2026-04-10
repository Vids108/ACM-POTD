                                                    Remove Outermost Parentheses
This problem involves removing the outermost parentheses from every primitive valid substring in a given parentheses string. A primitive
substring is a non-empty valid parentheses string that cannot be split further into smaller valid parts.
The solution uses a depth counter to track the level of nesting while traversing the string. When encountering
an opening parenthesis, it is added to the result only if the current depth is greater than zero, ensuring outermost
ones are skipped. For closing parentheses, the depth is decreased first, and the character is added only if the updated depth
remains greater than zero. This ensures correct removal in O(n) time.

CODE:
class Solution {
    public String removeOuterParentheses(String s) {
        StringBuilder result = new StringBuilder();
        int depth = 0;

        for (char c : s.toCharArray()) {
            if (c == '(') {
                if (depth > 0) result.append(c);
                depth++;
            } else {
                depth--;
                if (depth > 0) result.append(c);
            }
        }

        return result.toString();
    }
}
                                                      
