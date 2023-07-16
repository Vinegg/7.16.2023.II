# 7.16.2023.II
二分法求有序数组中某数的下标.II
# 7.16.2023
二分法求有序数组中某数的下标
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int arr[] = { 1,2,3,4,5,6,7,8,9,10 };
	int k = 17;
	int sz = sizeof(arr) / sizeof(arr[0]);//找到数组中元素个数
	int left = 0;
	int right = sz - 1;
	while (left <= right)//等号不能去
	{
		int mid = (left + right) / 2;//求mid的时候应该把式子放进while中，因为二分查找需要不断重复除以2这个过程。
		int mid=left+(right-left)/2;//这么写可以避免因为左端加右端数字过大导致溢出，如果此时right不会溢出那么将right多出部分折半给left也不会溢出，相比上式要好一点
                  if (arr[mid] < k)
		{
			left = mid + 1;
		}
		else if (arr[mid] > k)
		{
			right = mid - 1;
		}
		else
		{
			printf("找到了，下标是:%d\n", mid);
			break;
		}
	}
	if (left > right)
	{
		printf("找不到\n");
	}
	return 0;
}
