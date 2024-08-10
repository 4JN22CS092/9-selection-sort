# 9-selection-sort

Selection Sort:
#include<stdio.h>
#include<time.h>
#include<stdlib.h>
#include<conio.h>
void selection(int arr[], int n)
{
int i, j, small;
for (i = 0; i < n-1; i++) // One by one move boundary of unsorted subarray
{
small = i; //minimum element in unsorted array
for (j = i+1; j < n; j++)
if (arr[j] < arr[small])
small = j;
// Swap the minimum element with the first element
int temp = arr[small];
arr[small] = arr[i];
arr[i] = temp;
}
}
void main()
{
int a[200],i,n;
clock_t s,e;
printf("enter the size of unsorted list\n");
scanf("%d",&n);
for(i=0;i<n;i++)
{
a[i]=rand();
}
printf("an usorted list is\n");
for(i=0;i<n;i++)
{
printf("%d ",a[i]);
}
s=clock();
selection(a, n);
e=clock();
printf("the sorted list is\n");
for(i=0;i<n;i++)
{
printf("%d ",a[i]);
}
printf("\n total time taken=%f\n",(double)(e-s)/CLOCKS_PER_SEC);
}
