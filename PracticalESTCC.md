
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main() {
    int n, m;
    cout << "Enter size of first array: ";
    cin >> n;
    vector<int> a(n);
    cout << "Enter first array elements: ";
    for(int i = 0; i < n; i++) {
        cin >> a[i];
    }
    cout << "Enter size of second array: ";
    cin >> m;
    vector<int> b(m);
    cout << "Enter second array elements: ";
    for(int i = 0; i < m; i++) {
        cin >> b[i];
    }
    sort(a.begin(), a.end());
    sort(b.begin(), b.end());
    vector<int> c(n + m);
    merge(a.begin(), a.end(), b.begin(), b.end(), c.begin());
    cout << "Merged sorted array: ";
    int sum = 0;
    for(int i = 0; i < n + m; i++) {
        cout << c[i] << " ";
        sum += c[i];
    }
    double mean = (double)sum / (n + m);
    cout << "\nMean = " << mean;
    return 0;
}
