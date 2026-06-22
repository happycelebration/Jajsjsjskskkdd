# Yahan par aapko niche code milega


class Solution {
public:
vector<int> smallestSufficientTeam(vector<string>& req_skills,
vector<vector<string>>& people) { int n = req_skills.size();bunordered_map<string,int> skillId; for(int i = 0; i < n; i++) skillId[req_skills[i]] = i;
int target = (1 << n) - 1; vector<vector<int>> dp(1 << n); vector<bool> vis(1 << n, false); vis[0] = true;
for(int i = 0; i < people.size(); i++) { int personMask = 0; for(string& skill : people[i]) if(skillId.count(skill)) personMask |= 1 << skillId[skill];
auto curDp = dp; auto curVis = vis; for(int mask = 0; mask <= target; mask++) { if(!curVis[mask])
 continue; int newMask = mask | personMask;
if(!vis[newMask] || dp[newMask].size() > curDp[mask].size() + 1) { dp[newMask] = curDp[mask]; dp[newMask].push_back(i);
vis[newMask] = true; }}} return dp[target]; }};
