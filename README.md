# Yahan par aapko niche code milega


class Solution {
public:
vector<int> res; int i = 0; void dfs(TreeNode* root, vector<int>& voyage) { if (!root) return; if (root->val != voyage[i]) { res.clear(); res.push_back(-1); return;
} i++; if (root->left && i < voyage.size() && root->left->val != voyage[i]) { res.push_back(root->val);
dfs(root->right, voyage); dfs(root->left, voyage); } else { dfs(root->left, voyage); dfs(root->right, voyage); }} vector<int> flipMatchVoyage(TreeNode* root, vector<int>& voyage) { dfs(root, voyage); if (!res.empty() && res[0] == -1) return {-1}; return res; }};
