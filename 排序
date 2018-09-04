#include<iostream>
using namespace std;
int count = 0;
// 快排
void QuickSort(int arr[], int begin, int end);
int Partition(int arr[], int begin, int end);
// 归并
void MergeSort(int arr[], int begin, int end);
void Merge(int arr[], int begin, int mid, int end);
// 堆排
void HeapSort(int arr[], int len);
void HeapAdjust(int arr[], int begin, int end);
void swap(int arr[], int i, int j)
{
	int temp = arr[i];
	arr[i] = arr[j];
	arr[j] = temp;
}

void show(int arr[], int n)
{
	for(int i=0;i<n;i++)
		cout<<arr[i]<<" ";
	cout<<endl;
}
int main()
{
	int arr1[10] = {9, 2, 1, 6, 4, 3, 8, 5, 7 ,0};
	QuickSort(arr1, 0, 9);
	cout<<"QuickSort: "; show(arr1, 10);


	int arr2[10] = {9, 2, 1, 6, 4, 3, 8, 5, 7 ,0};
	MergeSort(arr2, 0, 9);
	cout<<"MergeSort: "; show(arr2, 10);

	int arr3[10] = {9, 2, 1, 6, 4, 3, 8, 5, 7 ,0};
	HeapSort(arr3, 10);
	cout<<"HeapSort: "; show(arr3, 10);
	return 0;
}
void QuickSort(int arr[], int begin, int end)
{
	if(begin<end)
	{
		int pivot = Partition(arr, begin, end);
		QuickSort(arr, begin, pivot-1);
		QuickSort(arr, pivot+1, end);
	}
}

int Partition(int arr[], int begin, int end)
{
	int pivot = arr[begin];
	int i = begin;
	for(int j=i+1; j<=end; j++)
	{
		if(arr[j]<pivot)
		{
			i++;
			swap(arr, i, j);
		}
	}
	swap(arr, begin, i);
	return i;
}

void MergeSort(int arr[], int begin, int end)
{
	if(begin<end)
	{
		int mid = (begin+end)/2;
		MergeSort(arr, begin, mid);
		MergeSort(arr, mid+1, end);
		Merge(arr, begin, mid, end);
	}
}

void Merge(int arr[], int begin, int mid, int end)
{
	int length1 = mid-begin+1;
	int length2 = end - mid;
	int * arr1 = new int[length1];
	int * arr2 = new int[length2];
	for(int i=0; i<length1; i++)
		arr1[i] = arr[begin + i];
	for(int j=0; j<length2; j++)
		arr2[j] = arr[mid+1+j];

	int i=0, j=0;
	while(i<length1 && j<length2)
	{
		if(arr1[i]<=arr2[j])
			arr[begin++] = arr1[i++];
		else
			arr[begin++] = arr2[j++];
	}
	while(i<length1)
		arr[begin++] = arr1[i++];
	while(j<length2)
		arr[begin++] = arr2[j++];
	delete [] arr1;
	delete [] arr2;
}

void HeapSort(int arr[], int len)
{
	for(int i=(len-1)/2; i>=0; i--)
		HeapAdjust(arr, i, len);
	for(int i=len-1; i>=0; i--)
	{
		swap(arr, 0, i);
		HeapAdjust(arr, 0, i);
	}
}

void HeapAdjust(int arr[], int low, int high)
{
	int temp = arr[low];
	for(int j=2*low+1; j<high; j=2*low+1){
		if(j+1<high && arr[j+1]>arr[j])
			j++;
		if(temp>arr[j])
			break;
		arr[low] = arr[j];
		low = j;
	}
	arr[low] = temp;
}
