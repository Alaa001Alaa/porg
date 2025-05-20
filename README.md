# porg




#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main() {
    int n;
    cin >> n; // عدد العملات
    vector<int> coins(n);
    int total = 0;

    for (int i = 0; i < n; i++) {
        cin >> coins[i];
        total += coins[i]; // مجموع كل العملات
    }

    // ترتيب العملات تنازليًا
    sort(coins.rbegin(), coins.rend());

    int my_sum = 0;
    int count = 0;

    for (int i = 0; i < n; i++) {
        my_sum += coins[i];
        count++;
        if (my_sum > total - my_sum) {
            break;
        }
    }

    cout << count << endl;
    return 0;
}
