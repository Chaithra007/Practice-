PROBLEM STATEMENT 

Given two sorted arrays arr1[] and arr2[] of sizes n and m in non-decreasing order.

Merge them in sorted order without using any extra space. Modify arr1 so that it contains the first N elements and modify arr2 so that it contains the last M elements.

CODE
```
void merge(long long arr1[], long long arr2[], int n, int m) 
        { 
            // code here 
            int i=n-1;
            int j=0;
            while(i>=0 && j<m)
            {
                if(arr1[i]>arr2[j])
                {
                    int temp=arr1[i];
                    arr1[i]=arr2[j];
                    arr2[j]=temp;
                }
                else
                {
                    i--;
                    j++;
                    continue;
                }
                i--;
                j++;
            }
            sort(arr1,arr1+n);
            sort(arr2,arr2+m);
        }
```

**DESCRIPTION**

We know that all the elements in the first array after performing the operation will the less than all the elements in the second array.

since all the elements in the array is already sorted we compare the last element of the first array and the first element of the second array if the element in the first array is greater than the element in the second array then we swap the elements.

Then we move the pointers one step ahead .

We continue this process until one of the array is exhausted 

Then we swap both the arrays individually 

![1687522930609](https://github.com/Chaithra007/Practice-/assets/107351787/e8896913-a5d2-49e3-a404-9e4275de0484)
