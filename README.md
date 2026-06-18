# Yahan par aapko niche code milega


class Solution {
public:
int countTriplets(vector<int>& nums) { const int MAX_MASK = 1 << 16; vector<int> cnt(MAX_MASK, 0); for (int a : nums) { for (int b : nums) { cnt[a & b]++; }} int ans = 0; for (int mask = 0; mask < MAX_MASK; mask++) { if (cnt[mask] == 0) continue; for (int z : nums) { if ((mask & z) == 0) { ans += cnt[mask]; }}} return ans; }};
