class Solution {
public:
    string removeOuterParentheses(string s) {
        string result;
        int balance = 0;
        int n = s.size();
        for (int i = 0; i < n; i++) {
            if (s[i] == '(') {
                if (balance > 0) {
                    result += s[i]; 
                }
                balance++; 
            } else {
                balance--;
                if (balance > 0) {
                    result += s[i]; 
                }
            }
        }

        return result; 
    }
};