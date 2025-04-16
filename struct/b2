#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct Svien
{
    char ho_ten[100];
    int tuoi;
    float diem_tb;

    struct Svien *next;
} Svien;

Svien *create(const char *ho_ten, int tuoi, float diem_tb)
{
    Svien *new_svien = (Svien *)malloc(sizeof(Svien));

    strcpy(new_svien -> ho_ten, ho_ten);
    new_svien -> tuoi = tuoi;
    new_svien -> diem_tb = diem_tb;

    return new_svien;
}

void add(Svien **head, const char *ho_ten, int tuoi, float diem_tb)
{
    Svien *new_svien = create(ho_ten, tuoi, diem_tb);
    new_svien -> next = *head;
    *head = new_svien;
}

int insert_name(Svien **head, const char *tar_ho_ten, const char *ho_ten, int tuoi, float diem_tb)
{
    Svien *new_svien = create(ho_ten, tuoi, diem_tb);
    Svien *tmp = *head;

    if(strcmp(tmp -> ho_ten, tar_ho_ten) == 0)
    {
        new_svien -> next = *head;
        *head = new_svien;
    }
    else
    {
        Svien *tmpp = NULL;
        while (tmp != NULL && strcmp(tmp -> ho_ten, tar_ho_ten) != 0)
        {
            tmpp = tmp;
            tmp = tmp -> next;
        }

        if(tmp == NULL)
        {
            return -1;
        }

        new_svien -> next = tmp;
        tmpp -> next = new_svien;
    }
    return 0;
}

int delete_sv(Svien **head, const char *tar_ho_ten)
{
    Svien *tmp = *head;

    if(tmp != NULL && strcmp(tmp -> ho_ten, tar_ho_ten) == 0)
    {
        *head = tmp -> next;
        free(tmp);
    }
    else
    {
        Svien *tmpp = NULL;
        while (tmp != NULL && strcmp(tmp -> ho_ten, tar_ho_ten) != 0)
        {
            tmpp = tmp;
            tmp = tmp -> next;
        }

        if(tmp == NULL)
            return -1;

        tmpp -> next = tmp -> next;
        free(tmp);
    }
    return 0;
}

void print(Svien **head)
{
    Svien *tmp = *head;
    int res = 1;

    printf("\n\t\t DANH SACH SINH VIEN\n");
    printf("%-3s %-25s %-5s %-5s\n", "STT", "Ho ten", "Tuoi", "Diem TB");
    while (tmp != NULL)
    {
        printf("%-3d %-25s %-5d %.2f\n",
               res, tmp -> ho_ten, tmp -> tuoi, tmp -> diem_tb);

        res++;
        tmp = tmp -> next;
    }

}

int main()
{
    Svien *head = NULL;

    char ho_ten[100], ho_ten_c[100];
    int tuoi;
    float diem_tb;


    int n;
    printf("Nhap so luong sinh vien: ") ;
    scanf("%d", &n);
    for(int i = 0; i < n; i++)
    {
        printf("Sinh vien thu %d\n", i + 1);

        printf("Ho ten: ");
        while (getchar() != '\n');
        fgets(ho_ten, 100, stdin);
        ho_ten[strlen(ho_ten) - 1] = '\0';

        printf("Tuoi: ");
        scanf("%d", &tuoi);
        printf("Diem TB: ");
        scanf("%f", &diem_tb);

        add(&head, ho_ten, tuoi, diem_tb);
        printf("\n");
    }

    print(&head);

    int exit = 0;
    while(!exit)
    {
        printf("\n\n");
        printf("0. Thoat\n");
        printf("1. Them sinh vien\n");
        printf("2. Xoa sinh vien\n");
        printf("3. Chen sinh vien\n");

        int inp;

        printf("Nhap lua chon: ");
        scanf("%d", &inp);

        switch(inp)
        {
        case 0:
        {
            exit = 1;
            break;
        }
        case 1:
        {
            printf("Ho ten: ");
            while (getchar() != '\n');
            fgets(ho_ten, 100, stdin);
            ho_ten[strlen(ho_ten) - 1] = '\0';

            printf("Tuoi: ");
            scanf("%d", &tuoi);
            printf("Diem TB: ");
            scanf("%f", &diem_tb);

            add(&head, ho_ten, tuoi, diem_tb);
            printf("\n");
            print(&head);
            break;
        }
        case 2:
        {
            printf("nhap ho ten SV can xoa: ");
            while (getchar() != '\n');
            fgets(ho_ten, 100, stdin);
            ho_ten[strlen(ho_ten) - 1] = '\0';

            if(delete_sv(&head, ho_ten) == -1)
            {
                printf("Khong tim thay sinh vien ten %s\n", ho_ten_c);
            }
            else
            {
                printf("Xoa thanh cong!\n");
                print(&head);
            }
            break;
        }
        case 3:
        {
            printf("Ho ten can chen: ");
            while (getchar() != '\n');
            fgets(ho_ten_c, 100, stdin);
            ho_ten_c[strlen(ho_ten_c) - 1] = '\0';

            printf("Ho ten: ");
            fgets(ho_ten, 100, stdin);
            ho_ten[strlen(ho_ten) - 1] = '\0';

            printf("Tuoi: ");
            scanf("%d", &tuoi);
            printf("Diem TB: ");
            scanf("%f", &diem_tb);

            if(insert_name(&head, ho_ten_c, ho_ten, tuoi, diem_tb) == -1)
            {
                printf("Khong tim thay sinh vien ten %s\n", ho_ten_c);
            }
            else
            {
                printf("Chen thanh cong!\n");
                print(&head);
            }
            break;
        }

        default:
            printf("Loi\n");
            break;
        }
    }

    free(head);
}
