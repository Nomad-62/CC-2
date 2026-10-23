#include <iostream>
using namespace std;
int climbStairs(int n) {
    if (n <= 2) {
        return n;
    }
    int prev1 = 1;
    int prev2 = 2;
    for (int i = 3; i <= n; i++) {
        int current = prev1 + prev2;
        prev2 = prev1;
        prev1 = current;
    }
    return prev1;
}
int main() {
    int n;
    cin >> n;
    cout << climbStairs(n) << endl;
    return 0;
}
