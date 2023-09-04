#include <stdio.h>
void swap(int a[],int i,int j)
{
    int t=a[i];
    a[i]=a[j];
    a[j]=t;
}
int partition(int a[],int l,int r)
{
    int i=l+1,j=r,p=a[l];
    while(i<j)
    {
        while(p>a[i])
        {
            i++;
        }
        while(p<=a[j])
        {
            j--;
        }
        if(i<j)
        {
            swap(a,i,j);
        }
        else
        {
            swap(a,l,j);
            return j;
        }
    }
}
void quicksort(int a[],int l,int r)
{
    int p;
    if(l<r)
    {
        p=partition(a,l,r);
        quicksort(a,l,p-1);
        quicksort(a,p+1,r);
    }
}
int main() 
{
    int a[10],n;
    printf("Enter size of array:");
    scanf("%d",&n);
    printf("Enter array elements:");
    for (int i=0; i<n; i++)
    {
         scanf("%d",&a[i]);
    }
    printf("The array elements are:");
    for (int i=0; i<n; i++)
    {
         printf("%d ",a[i]);
    }
    quicksort(a,0,n-1);
    printf("\nthe sorted array is:");
    for (int i=0; i<n; i++)
    {
         printf("%d ",a[i]);
    }
    return 0;
}
