# Yahan par aapko niche code milega


class Solution {
public:
vector<int> sumEvenAfterQueries(vector<int>& nums, vector<vector<int>>& queries) { int evenSum = 0; for (int x : nums) { if (x % 2 == 0)
 evenSum += x; } vector<int> ans; for (auto &q : queries) { int val = q[0];bint idx = q[1]; if (nums[idx] % 2 == 0) evenSum -= nums[idx]; nums[idx] += val;
 if (nums[idx] % 2 == 0) evenSum += nums[idx];
ans.push_back(evenSum); } return ans; }};
