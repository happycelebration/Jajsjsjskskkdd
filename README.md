# Yahan par aapko niche code milega


class Solution {
public:
string strWithout3a3b(int a, int b) { string ans;
while (a > 0 || b > 0) { int n = ans.size(); bool writeA = false; if (n >= 2 && ans[n - 1] == ans[n - 2]) { if (ans[n - 1] == 'b') writeA = true; } else { if (a >= b) writeA = true; } if (writeA) { ans += 'a'; a--; } else {
ans += 'b'; b--; }} return ans; }};
