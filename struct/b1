#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct {
    char name[100];
    long long price, quan, sum;
} prod;

void sort_name(prod *db, int sz) {
    prod tmp;
    for(int i = 0; i < sz; i++) {
        for(int j = i + 1; j < sz; j++) {
            if(strcmp(db[i].name, db[j].name) > 0) {
                tmp = db[i];
                db[i] = db[j];
                db[j] = tmp;
            }
        }
    }
}

void out(prod *db, int n) {
    sort_name(db, n);

    printf("\t\t SO LIEU BAN HANG\n");
    printf("%-3s %-15s %-10s %-10s %-15s\n", "STT", "Ten Hang", "Don gia", "So luong", "Thanh tien");

    long long sum_a = 0;
    for (int i = 0; i < n; i++) {
        printf("%-3d %-15s %-10lld %-10lld %-15lld\n",
               i + 1, db[i].name, db[i].price, db[i].quan, db[i].sum);
        sum_a += db[i].sum;
    }

    printf("%-3s %-15s %-10s %-10s %-15lld\n", "", "", "", "TONG TIEN", sum_a);
}


int main() {
    prod *db = NULL;
    int n;

    printf("Nhap so luong mat hang: "); scanf("%d", &n);

    db = (prod *)calloc(n, sizeof(prod));
    for(int i = 0; i < n; i++) {
        printf("Mat hang thu %d\n", i + 1);

        printf("Ten hang: ");
        while (getchar() != '\n');
        fgets(db[i].name, 100, stdin);
        db[i].name[strlen(db[i].name) - 1] = '\0';

        printf("Don gia: "); scanf("%lld", &db[i].price);
        printf("So luong: "); scanf("%lld", &db[i].quan);
        printf("\n");
        db[i].sum = db[i].price * db[i].quan;
    }

    out(db, n);

    free(db);
}
