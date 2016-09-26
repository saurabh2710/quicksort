# quicksort


#include<iostream>
using namespace std;
void quicksort(int,int,int);
int partition(int,int,int);

int partition(int arr[],int start,int end)
{
	int index=start;
	int pivot=arr[end];
	for(int i=start;i<end;i++)
	{
		if(arr[i]<=pivot)
		{
			swap(arr[i],arr[index]);
			index++;
		}
	}
	swap(arr[index],arr[end]);
	return index;
	
}
void swap(int a,int b)
{
	int temp;
	temp=a;
	a=b;
	b=temp;
}
void quicksort(int arr[],int start,int end)
{
	if(start<end)
	{
	int index=partition(arr,start,end);
	quicksort(arr,start,index-1);
	quicksort(arr,index+1,end);
   }
}
main()
{
	cout<<"enter the size of the array"<<endl;
	int n,d;
	cin>>n;
	int arr[n];
	cout<<"enter the elements"<<endl;
	for(int i=0;i<n;i++)
	{
		cin>>arr[i];
		
	}
	quicksort(arr,0,n-1);
	for(int i=0;i<n;i++)
	{
		cout<<arr[i]<<" ";
	}
}
