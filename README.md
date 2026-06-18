# Yahan par aapko niche code milega


class Solution {
public:
int numRookCaptures(vector<vector<char>>& board) { int rx = -1, ry = -1; for (int i = 0; i < 8; i++) {
for (int j = 0; j < 8; j++) { if (board[i][j] == 'R') { rx = i;
 ry = j; }}} vector<pair<int,int>> dirs = { {-1, 0}, {1, 0},
{0, -1}, {0, 1} }; int ans = 0; for (auto &[dx, dy] : dirs) { int x = rx + dx; int y = ry + dy; while (x >= 0 && x < 8 && y >= 0 && y < 8) { if (board[x][y] == 'B') break;
 if (board[x][y] == 'p') { ans++; break; } x += dx; y += dy; }} return ans; }};
