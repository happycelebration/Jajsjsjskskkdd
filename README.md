# Yahan par aapko niche code milega


class Solution {
public:
long long findKthSmallest(vector<int>& coins, int k) { int n = coins.size(); long long lo = 1; long long hi = 1LL * k * (*min_element(coins.begin(), coins.end())); auto gcd = [](long long a, long long b) {
 while (b) { long long t = a % b; a = b; b = t; } return a; }; auto lcm = [&](long long a, long long b) { return a / gcd(a, b) * b; }; auto count = [&](long long x) { long long total = 0; for (int mask = 1; mask < (1 << n); ++mask) { long long common = 1;
bool valid = true; for (int i = 0; i < n; ++i) { if (mask & (1 << i)) { common = lcm(common, coins[i]); if (common > x) { valid = false; break; }}} if (!valid)
continue; long long cur = x / common; if (__builtin_popcount(mask) & 1) total += cur; else
total -= cur; } return total; }; while (lo < hi) { long long mid = lo + (hi - lo) / 2; if (count(mid) >= k) hi = mid; else lo = mid + 1; } return lo; }};
