# Yahan par aapko niche code milega


class Solution {
public:
int oddEvenJumps(vector<int>& arr) { int n = arr.size(); vector<int> nextHigher(n, -1), nextLower(n, -1); vector<pair<int,int>> v; for (int i = 0; i < n; i++) {
v.push_back({arr[i], i});} sort(v.begin(), v.end()); 
stack<int> st; for (auto &p : v) { int i = p.second;
while (!st.empty() && st.top() < i) { nextHigher[st.top()] = i; st.pop(); } st.push(i); } v.clear(); for (int i = 0; i < n; i++) { v.push_back({-arr[i], i}); }
sort(v.begin(), v.end()); while (!st.empty()) st.pop();
for (auto &p : v) { int i = p.second; while (!st.empty() && st.top() < i) { nextLower[st.top()] = i; st.pop(); } st.push(i); } vector<bool> odd(n, false), even(n, false); odd[n - 1] = even[n - 1] = true; for (int i = n - 2; i >= 0; i--) { if (nextHigher[i] != -1) odd[i] = even[nextHigher[i]]; if (nextLower[i] != -1) even[i] = odd[nextLower[i]]; } int ans = 0; for (int i = 0; i < n; i++) { if (odd[i]) ans++; } return ans; }};
