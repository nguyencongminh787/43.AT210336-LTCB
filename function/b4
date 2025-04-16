#include <stdio.h>

void inp(int n, int m, int tmp[100][100]) {
    for(int i = 0; i < n; i++) {
        for(int j = 0; j < m; j++) 
            scanf("%d", &tmp[i][j]);
    }
}

void out(int n, int m, int tmp[100][100]) {
    for(int i = 0; i < n; i++) {
        for(int j = 0; j < m; j++) {
            printf("%d ", tmp[i][j]);
        }
        printf("\n");
    }
}

void pls(int n, int m, int a[100][100], int b[100][100], int tmp[100][100]) {
    for(int i = 0; i < n; i++) {
        for(int j = 0; j < m; j++)
            tmp[i][j] = a[i][j] + b[i][j];
    }
}

void mul(int n, int m, int a[100][100], int b[100][100], int tmp[100][100]) {
    for(int i = 0; i < n; i++) {
        for(int j = 0; j < m; j++) {
            int res = 0;
            for(int k = 0; k < m; k++) {
                res += (a[i][k] * b[k][j]);
            }
            tmp[i][j] = res;
        }
    }
}

int main() {
    int n, m;
    int a[100][100], b[100][100], pl[100][100], mu[100][100];

    printf("Nhap so hang: "); scanf("%d", &n);
    printf("Nhap so cot: "); scanf("%d", &m);

    printf("Nhap ma tran a: \n");
    inp(n, m, a);

    printf("Nhap ma tran b: \n");
    inp(n, m, b);

    pls(n, m, a, b, pl);
    mul(n, m, a, b, mu);

    printf("Tong 2 ma tran la: \n");
    out(n, m, pl);

    printf("Tich 2 ma tran la: \n");
    out(n, m, mu);
}
