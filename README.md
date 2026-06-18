# Yahan par aapko niche code milega


class Solution {
public:
 int m, n; int total = 0; int ans = 0; vector<int> dir = {0, 1, 0, -1, 0}; void dfs(vector<vector<int>>& grid, int x, int y, int count) { if (grid[x][y] == 2) { if (count == total) ans++; return; } int temp = grid[x][y];
grid[x][y] = -2; for (int k = 0; k < 4; k++) { int nx = x + dir[k]; int ny = y + dir[k + 1]; if (nx < 0 || ny < 0 || nx >= m || ny >= n) continue; if (grid[nx][ny] == -1 || grid[nx][ny] == -2) continue; dfs(grid, nx, ny, count + 1); } grid[x][y] = temp; } int uniquePathsIII(vector<vector<int>>& grid) { m = grid.size(); n = grid[0].size(); int sx, sy; for (int i = 0; i < m; i++) { for (int j = 0; j < n; j++) { if (grid[i][j] != -1) total++; if (grid[i][j] == 1) { sx = i; sy = j; }}}
dfs(grid, sx, sy, 1); return ans; }};
