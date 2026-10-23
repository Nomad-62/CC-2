
#include <iostream>
#include <vector>
#include <algorithm>
#include <cstdlib>
#include <climits>
using namespace std;

int frogJump(int n, int k, vector<int>& height) {
    vector<int> dp(n, INT_MAX);
    dp[0] = 0;

    for (int i = 1; i < n; i++) {
        for (int j = max(0, i - k); j < i; j++) {
            int cost = dp[j] + abs(height[i] - height[j]);
            dp[i] = min(dp[i], cost);
        }
    }

    return dp[n - 1];
}

int main() {
    int n, k;
    cin >> n >> k;

    vector<int> height(n);
    for (int i = 0; i < n; i++) {
        cin >> height[i];
    }

    cout << frogJump(n, k, height) << endl;

    return 0;
}
