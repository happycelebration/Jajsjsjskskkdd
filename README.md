# Yahan par aapko niche code milega


class Solution {
public:
vector<int> days, costs; vector<int> dp; int n; int dfs(int i) { if (i >= n) return 0; if (dp[i] != -1) return dp[i]; int ans = INT_MAX; vector<int> duration = {1, 7, 30}; for (int k = 0; k < 3; k++) { int coverUntil = days[i] + duration[k]; int j = lower_bound( days.begin(), days.end(), coverUntil ) - days.begin();
 ans = min(ans, costs[k] + dfs(j)); } return dp[i] = ans; } int mincostTickets(vector<int>& d, vector<int>& c) { days = d; costs = c; n = days.size(); dp.assign(n, -1); return dfs(0); }};
