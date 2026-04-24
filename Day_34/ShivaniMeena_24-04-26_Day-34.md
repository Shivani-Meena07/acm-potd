class Solution {
public:
    int rob(vector<int>& nums) {
        int n = nums.size();
        if(n == 1) return nums[0];
        
        vector<int> dp(n);
        dp[0] = nums[0], dp[1] = nums[1];
        if(n > 2) dp[2] = nums[2] + dp[0];
        else return max(dp[0], dp[1]);

        for(int i = 3; i < n; i++)
        {
            dp[i] = nums[i] + max(dp[i - 2], dp[i - 3]);
        }

        return max(dp[n - 2], dp[n - 1]);
    }
};