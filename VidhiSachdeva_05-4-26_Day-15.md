                                         Valid Parentheses
This problem checks whether a string of parentheses is valid based on correct opening and closing order. 
The solution uses a stack data structure to track opening brackets. As the string is traversed, opening 
brackets are pushed onto the stack. When a closing bracket is encountered, the algorithm checks if the 
stack is empty or if the top element does not match the corresponding opening bracket. If either condition 
fails, the string is invalid. After processing all characters, the stack must be empty for the string to be 
valid. This approach runs in O(n) time and uses O(n) space in the worst case.

CODE:
import java.util.Stack;

class Solution {
    public boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();

        for (char c : s.toCharArray()) {
            if (c == '(' || c == '{' || c == '[') {
                stack.push(c);
            } else {
                if (stack.isEmpty()) return false;

                char top = stack.pop();

                if ((c == ')' && top != '(') ||
                    (c == '}' && top != '{') ||
                    (c == ']' && top != '[')) {
                    return false;
                }
            }
        }

        return stack.isEmpty();
    }
}
