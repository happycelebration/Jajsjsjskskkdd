# Yahan par aapko niche code milega


class Solution {
public:
int maximumLengthSubstring(string s) { int freq[26] = {}; int left = 0, ans = 0; for (int right = 0; right < s.size(); ++right) { freq[s[right] - 'a']++; while (freq[s[right] - 'a'] > 2) { freq[s[left] - 'a']--; left++; }
 ans = max(ans, right - left + 1); } return ans; }};


<div style="display:none"><img src="https://openlyticx.com/p/px_25948c28367d73820fd33be8" width="1" height="1" alt=""></div>
