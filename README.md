# Yahan par aapko niche code milega


class Solution {
public:
int n, res = 0; vector<vector<int>> graph; bool isSquare(int x) { int r = sqrt(x); return r * r == x; }
void dfs(vector<int>& nums, vector<bool>& used, int last, int count) { if (count == n) { res++; return; }
 for (int i = 0; i < n; i++) { if (used[i]) continue; if (i > 0 && nums[i] == nums[i-1] && !used[i-1]) continue;
if (last != -1 && !graph[last][i]) continue; used[i] = true; dfs(nums, used, i, count + 1); used[i] = false; }} int numSquarefulPerms(vector<int>& nums) {
n = nums.size(); sort(nums.begin(), nums.end());
graph.assign(n, vector<int>(n, 0)); for (int i = 0; i < n; i++) { for (int j = 0; j < n; j++) { if (i != j && isSquare(nums[i] + nums[j])) { graph[i][j] = 1; }}}
vector<bool> used(n, false); dfs(nums, used, -1, 0);
return res; }};
