# Yahan par aapko niche code milega


class Solution {
public:
vector<TreeNode*> ans; unordered_set<int> del;
 TreeNode* dfs(TreeNode* root) { if (!root) return nullptr; root->left = dfs(root->left); root->right = dfs(root->right); if (del.count(root->val)) { if (root->left) ans.push_back(root->left); if (root->right) ans.push_back(root->right); return nullptr; }
return root; } vector<TreeNode*> delNodes(TreeNode* root, vector<int>& to_delete) { del = unordered_set<int>(to_delete.begin(), to_delete.end()); root = dfs(root); if (root) ans.push_back(root); return ans; }};
