class Solution {
public:
    vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int color) {
        int orig = image[sr][sc];
        if (orig == color) return image;

        function<void(int,int)> dfs = [&](int r, int c) {
            if (r < 0 || r >= image.size() || c < 0 || c >= image[0].size() || image[r][c] != orig)
                return;
            image[r][c] = color;
            dfs(r+1, c);
            dfs(r-1, c);
            dfs(r, c+1);
            dfs(r, c-1);
        };

        dfs(sr, sc);
        return image;
    }
};