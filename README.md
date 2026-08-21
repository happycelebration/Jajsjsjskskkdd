# Yahan par aapko niche code milega


class Solution {
public:
long long findKthSmallest(vector<int>& coins, int k) { int n = coins.size(); vector<long long> lcms(1 << n); for (int mask = 1; mask < (1 << n); ++mask) {
long long cur = 1; for (int i = 0; i < n; ++i) { if (mask & (1 << i)) { cur = lcm(cur, (long long)coins[i]); if (cur > 100000000000LL) { cur = 100000000000LL;
break; }}} lcms[mask] = cur; } auto count = [&](long long x) { long long total = 0; for (int mask = 1; mask < (1 << n); ++mask) { long long ways = x / lcms[mask]; if (__builtin_popcount(mask) & 1) total += ways; else total -= ways; if (total >= k) return total; } return total; }; long long left = 1; long long right = 1LL * k * *min_element(coins.begin(), coins.end()); while (left < right) { long long mid = left + (right - left) / 2; if (count(mid) >= k) right = mid; else left = mid + 1; } return left; }};
