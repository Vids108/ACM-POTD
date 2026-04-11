                                          Make The String Great
  This problem requires removing adjacent characters from a string where the same letter appears 
  in both lowercase and uppercase forms. The solution uses a stack-like approach implemented with a 
  StringBuilder. As each character is processed, it is compared with the last character in the result. 
  If their ASCII difference is 32, it means they are the same letter in different cases, so the last character 
  is removed. Otherwise, the current character is appended. This process continues until all characters are processed,
  naturally handling cascading removals. The algorithm runs in O(n) time and uses O(n) space for the result efficiently.

  CODE:
  class Solution {
    public String makeGood(String s) {
        StringBuilder sb = new StringBuilder();

        for (char c : s.toCharArray()) {
            int len = sb.length();

            if (len > 0 && Math.abs(sb.charAt(len - 1) - c) == 32) {
                sb.deleteCharAt(len - 1); 
            } else {
                sb.append(c);
            }
        }

        return sb.toString();
    }
}
