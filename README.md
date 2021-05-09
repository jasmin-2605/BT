# BT

//bai1

#include<stdio.h>

int main(){
    int a,b,n;
    printf("moi ban nhap a,b<n\n");
    int t=0;
    scanf("%d%d%d",&a,&b,&n);
    for(int i=a;i<=n;i++){
        if(i%a==0&&i%b!=0)
            t+=i;


    }
    printf("tong la: %d",t);
    return 0;
}



//bai2

#include<stdio.h>
#include<math.h>
int main(){

int n,i,j,s=0;
	do
	{
		printf("Nhap n:");scanf("%d",&n);
	}
	while(n<=0||n>=50);
	for(i=2;i<n;i++)

	{
	    int souoc=0;
		for(j=1;j<=i;j++)
		{
		if(i%j==0)
		souoc++;
		}
		if(souoc==2)
		s=s+i;
	}
	printf("Tong cua cac SNT nho hon %d la: %d",n,s);
	return 0;
}


//bai3

#include<stdio.h>

int main(){

    int a,b;
    printf("moi ban nhap 2 so a,b\n");
    scanf("%d%d",&a,&b);


    while(a!=b){
        if(a>b)
            a-=b;
        else
            b-=a;
    }
    printf("uscln:%d",a);
    return 0;
}



