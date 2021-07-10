//bai 1


#include <stdio.h>
#include <conio.h>

//doc so o hang tram nghin
unsigned int chucnghin(int x)
{
    switch(x){
        case 1:
            printf("Muoi");
            break;
        case 2:
            printf("Hai Muoi");
            break;
        case 3:
            printf("Ba Muoi");
            break;
        case 4:
            printf("Bon Muoi");
            break;
        case 5:
            printf("Nam Muoi");
            break;
        case 6:
            printf("Sau Muoi");
            break;
        case 7:
            printf("Bay Muoi");
            break;
        case 8:
            printf("Tam Muoi");
            break;
        case 9:
            printf("Chin Muoi");
            break;
        case 0:
            break;
    }
}

//doc so o hang nghin
unsigned int nghin(int x)
{
    switch(x){
        case 1:
            printf("Mot Nghin");
            break;
        case 2:
            printf("Hai Nghin");
            break;
        case 3:
            printf("Ba Nghin");
            break;
        case 4:
            printf("Bon Nghin");
            break;
        case 5:
            printf("Nam Nghin");
            break;
        case 6:
            printf("Sau Nghin");
            break;
        case 7:
            printf("Bay Nghin");
            break;
        case 8:
            printf("Tam Nghin");
            break;
        case 9:
            printf("Chin Nghin");
            break;
        case 0:
        	printf("nghin");
        	break;
    }
}

//doc so o hang tram
unsigned int tram(int x)
{
    switch(x){
        case 0:
            printf("Khong Tram");
            break;
        case 1:
            printf("Mot Tram");
            break;
        case 2:
            printf("Hai Tram");
            break;
        case 3:
            printf("Ba Tram");
            break;
        case 4:
            printf("Bon Tram");
            break;
        case 5:
            printf("Nam Tram");
            break;
        case 6:
            printf("Sau Tram");
            break;
        case 7:
            printf("Bay Tram");
            break;
        case 8:
            printf("Tam Tram");
            break;
        case 9:
            printf("Chin Tram");
            break;
    }
}

//doc so o hang chuc
unsigned int chuc(int x)
{
    switch(x){
        case 0:
            printf("linh");
            break;
        case 1:
            printf("Muoi");
            break;
        case 2:
            printf("Hai Muoi");
            break;
        case 3:
            printf("Ba Muoi");
            break;
        case 4:
            printf("Bon Muoi");
            break;
        case 5:
            printf("Nam Muoi");
            break;
        case 6:
            printf("Sau Muoi");
            break;
        case 7:
            printf("Bay Muoi");
            break;
        case 8:
            printf("Tam Muoi");
            break;
        case 9:
            printf("Chin Muoi");
            break;
    }
}

//doc so o hang don vi
unsigned int donvi(int x)
{
    switch(x){
        case 0:
            printf("Khong");
            break;
        case 1:
            printf("Mot");
            break;
        case 2:
            printf("Hai");
            break;
        case 3:
            printf("Ba");
            break;
        case 4:
            printf("Tu");
            break;
        case 5:
            printf("Lam");
            break;
        case 6:
            printf("Sau");
            break;
        case 7:
            printf("Bay");
            break;
        case 8:
            printf("Tam");
            break;
        case 9:
            printf("Chin");
            break;
    }
}



int main()
{
    int n;
    printf("\nNhap vao so tu 0 -> 99.999 :");
    scanf("%d",&n);

    //Tach cac so lan luot o hang tram nghin, chuc nhin, hang nghin, hang tram, hang chuc, hang don vi
    int cng= n/10000;
    int ng=(n/1000)%10;
    int t=(n/100)%10;
    int c=(n/10)%10;
    int dv=n%10;

   
    printf("\nDoc: ");
    if(cng!=0) chucnghin(cng); printf(" ");
    if(ng!=0)  nghin(ng);      printf(" ");
    if(t!=0)  tram(t);        printf(" ");
    if(c!=0) chuc(c);        printf(" ");
    if(dv!=0) donvi(dv);      printf(" ");
}

//bai 2

#include <stdio.h>
#include <stdlib.h>
#include<string.h>
#define Max_Len 105

typedef struct Node
{
    char Msv[Max_Len];
    char HoTen[Max_Len];
    float Luong;
    int stt;
    struct Node *next;

} Node;
Node *nodeLT;
typedef struct
{
    Node *dau;
    Node *cuoi;
} List;

void TaoDanhSachLienKet(List *plist)
{
    plist->dau=NULL;
    plist->cuoi=NULL;
}
Node* TaoNodemoi(char Msv[Max_Len], char HoTen[Max_Len], int stt, float Luong)
{
    Node *node=(Node*)malloc(sizeof(node));
    strcpy(node->Msv,Msv);
    strcpy(node->HoTen,HoTen);
    node->Luong=Luong;
    node->stt=stt;
    node->next=NULL;
    return node;
}
void ThemVaoDau(List *plist,char Msv[Max_Len], char HoTen[Max_Len], int stt, float Luong)
{
    Node *node=TaoNodemoi(Msv,HoTen,stt,Luong);
    plist->dau=node;
    plist->cuoi=node;
}
void ThemvaoDslk(List *plist,char Msv[Max_Len], char HoTen[Max_Len], int stt, float Luong)
{
    if(plist->dau==NULL)
    {
        ThemVaoDau(plist,Msv,HoTen,stt,Luong);
    }
    else
    {
        Node *node=TaoNodemoi(Msv,HoTen,stt,Luong);
        plist->cuoi->next=node;
        plist->cuoi=node;
    }
}
void NhapThongTin(List *plist)
{
    char Msv[Max_Len];
    char HoTen[Max_Len];
    int Stt;
    float Luong;
    printf("Nhap Ma Nv:");
    scanf("%s",Msv);
    getchar();
    printf("Nhap ten NV:");
    gets(HoTen);
    printf("Nhap Luong:");
    scanf("%f",&Luong);
    printf("Nhap STT:");
    scanf("%d",&Stt);
    fflush(stdin);
    ThemvaoDslk(plist,Msv,HoTen,Stt,Luong);
}
void inDanhSach(List *plist)
{
    Node *node=plist->dau;
    if(node!=NULL)
    {
        while(node!=NULL)
        {
            printf("%d\t%10s\t%7s\t\t%8.5f\n",node->stt,node->Msv,node->HoTen,node->Luong);
            node=node->next;
        }
    }
}

Node* TimkiemTen(List *plist,char Ten[])
{
    Node *node=plist->dau;
    if(node!=NULL)
    {
        while(node!=NULL)
        {
            if(strcmp(node->HoTen,Ten)==0)
            {
                return node;
            }
            nodeLT=node;
            node=node->next;
        }
    }
    return NULL;
}

void NhapvasuatheoTen(List *plist,char Ten[Max_Len],float Luong,char hotensua[Max_Len],char Mnv[Max_Len])
{

    Node *node=TimkiemTen(plist,Ten);
    if(node==NULL)
    {
        printf("Khong the sua thong tin nhan vien: %s\n",Ten);
    }
    else
    {
        node->Luong=Luong;
        strcpy(node->HoTen,hotensua);
        strcpy(node->Msv,Mnv);
    }

}

int main()
{
    int id,i,t,g=0;
    float Luong;
    char tentimkiem[Max_Len];
    char tensua[Max_Len];
    char Mnv[Max_Len];
    List *plist;
    plist=(List*)malloc(sizeof(List));
    TaoDanhSachLienKet(plist);
    do
    {

        printf("------------Menu-----------\n");
        printf("Chon 1 de nhap danh sach nhan vien \n");
        printf("Chon 2 de hien thi danh sach nhan vien\n");
        printf("Chon 3 de chen them mot nhan vien\n");
        printf("Chon 4 de sua thong tin nhan vien \n");
        printf("Chon 5 de ket thuc\n");
        printf("Nhap lua chon :");
        scanf("%d",&id);
        switch(id)
        {
        case 1:
            printf("Nhap So Luong nhan Vien:");
            scanf("%d",&t);
            for(i=0; i<t; i++)
            {

                NhapThongTin(plist);
                for(int j=0; j<t; j++)
                {

                    printf("Nhan Vien Tiep theo:\n");
                }
            }
            break;
        case 2:
            printf("           DANH SACH NHAN VIEN     \n");
            printf("STT     MA NHAN VIEN     TEN NHAN VIEN     LUONG\n");
            inDanhSach(plist);
            printf("\n");
            break;
        case 3:
            NhapThongTin(plist);
            break;
        case 4:
            printf("Nhap ten Nv can sua:");
            getchar();
            gets(tentimkiem);
            printf("Nhap Luong can sua :");
            scanf("%f",&Luong);
            printf("Nhap Ho ten sua :");
            getchar();
            gets(tensua);
            printf("Nhap Mnv sua:");
            getchar();
            scanf("%s",Mnv);
            NhapvasuatheoTen(plist,tentimkiem,Luong,tensua,Mnv);
            printf("\n");
            break;



        case 5:
            g++;
            break;
        }

    }
    while(g==0);
    return 0;
}

