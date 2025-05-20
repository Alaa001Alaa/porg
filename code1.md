#include <iostream>

using namespace std;
void read (int a[][4],int n ){
 for(int i=0;i<n;i++)
 for(int j=0;j<n;j++)
cin>>a[i][j];
}
void print (int a[][4],int n ){
 for(int i=0;i<n;i++){
 for(int j=0;j<n;j++)
cout<<a[i][j]<<"\t";
 cout<<"\n";}
}
void x(int a[][4],int n ,int r[], int f[]){//������ ����� ������� � ������ �� ������� ������
for(int i=0;i<n;i++)
 for(int j=0;j<n;j++)
if(i==j)
r[i]=a[i][j];
else if (i+j==(n-1))
    f[i]=a[i][j];
}
void TS(int a[],int n ){//��������
    int t;
for(int i=0;i<n;i++)
 for(int j=0;j<n;j++)
    if(a[j]>a[i]){
        t=a[i];
    a[i]=a[j];
    a[j]=t;}
}
void TN(int a[],int n ){//��������
    int t;
for(int i=0;i<n;i++)
 for(int j=0;j<n;j++)
    if(a[j]<a[i]){
        t=a[i];
    a[i]=a[j];
    a[j]=t;}
}
void return_arr(int a[][4],int n ,int r[], int f[]){//���� ����� ��� �������
for(int i=0;i<n;i++)
 for(int j=0;j<n;j++)
if(i==j)
a[i][j]=r[i];
else if (i+j==(n-1))
    a[i][j]=f[i];
}

int main()
{int n=4;
 int arr[4][4],r[n],f[n];
read(arr,n);
print(arr,n);
x(arr,n,r,f);
TS(r,n);
TN(f,n);
return_arr(arr,n,r,f);
cout<<"\n";
print(arr,n);
 return 0;
}

