# Yahan par aapko niche code milega


class Solution {
public:
int missingInteger(vector<int>& nums) { int sum = nums[0]; for (int i = 1; i < nums.size(); ++i) { if (nums[i] != nums[i - 1] + 1) break; sum += nums[i]; }
unordered_set<int> seen(nums.begin(), nums.end()); while (seen.count(sum)) ++sum; return sum; }};
