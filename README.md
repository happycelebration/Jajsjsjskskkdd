# Yahan par aapko niche code milega


class Solution {
public:
vector<int> pancakeSort(vector<int>& arr) { vector<int> res; int n = arr.size(); for (int i = n; i > 1; --i) { int idx = 0; for (int j = 0; j < i; ++j) { if (arr[j] == i) { idx = j; break; }} if (idx == i - 1) continue; if (idx != 0) { reverse(arr.begin(), arr.begin() + idx + 1);
res.push_back(idx + 1); } reverse(arr.begin(), arr.begin() + i); res.push_back(i); } return res; }};
