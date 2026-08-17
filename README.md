# Yahan par aapko niche code milega


class Solution { vector<vector<int>> dp; vector<int> prefix; vector<int> nums; int dfs(int l, int r) { if (l >= r) return 0; if (dp[l][r] != -1) return dp[l][r]; int ans = 0; int left = 0; int right = prefix[r + 1] - prefix[l]; for (int i = l; i < r; ++i) { left += nums[i];
right -= nums[i]; if (left < right) { if (ans > 2 * left)
continue; ans = max(ans, left + dfs(l, i)); }  else if (left > right) { if (ans > 2 * right) break; ans = max(ans, right + dfs(i + 1, r)); } else { ans = max({
 ans, left + dfs(l, i), right + dfs(i + 1, r)}); }} return dp[l][r] = ans; }
public:
int stoneGameV(vector<int>& stoneValue) { nums = stoneValue; int n = nums.size(); prefix.assign(n + 1, 0); for (int i = 0; i < n; ++i) prefix[i + 1] = prefix[i] + nums[i]; dp.assign(n, vector<int>(n, -1)); return dfs(0, n - 1); }};
