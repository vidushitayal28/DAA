#include <stdio.h>

int n, target, a[25];
int found[1 << 20], fc = 0;

void solve(int i, int sum, int mask) {
    if (sum == target && mask) found[fc++] = mask;
    if (i == n || sum >= target) return;
    for (int j = i; j < n; j++) {
        if (sum + a[j] > target) continue;
        solve(j + 1, sum + a[j], mask | (1 << j));
    }
}

int main() {
    scanf("%d", &n);
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);
    scanf("%d", &target);
    solve(0, 0, 0);
    if (fc == 0) {
        printf("-1\n");
        return 0;
    }
    for (int k = fc - 1; k >= 0; k--) {
        int first = 1;
        for (int j = 0; j < n; j++) {
            if (found[k] & (1 << j)) {
                printf("%d ", a[j]);
                first = 0;
            }
        }
        printf("\n");
    }
    return 0;
}
