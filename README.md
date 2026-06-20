# Yahan par aapko niche code milega


class Solution {
public:
vector<double> sampleStats(vector<int>& count) {
int mn = -1; int mx = -1; int mode = 0; long long sum = 0; long long total = 0; int maxFreq = 0; for (int i = 0; i < 256; i++) { if (count[i] > 0) { if (mn == -1) mn = i; mx = i; sum += 1LL * i * count[i]; total += count[i]; if (count[i] > maxFreq) { maxFreq = count[i]; mode = i; }}} auto kth = [&](long long k) -> int { long long pref = 0; for (int i = 0; i < 256; i++) {
pref += count[i]; if (pref >= k) return i; } return -1; };
double median; if (total % 2 == 1) { median = kth(total / 2 + 1); } else { int a = kth(total / 2); int b = kth(total / 2 + 1); median = (a + b) / 2.0; }
 return { (double)mn, (double)mx, (double)sum / total, median, (double)mode };}};
