PROBLEM STATEMENT 

Given a N x N 2D matrix Arr representing an image. Rotate the image by 90 degrees (anti-clockwise).
You need to do this in place. 
Note that if you end up using an additional array, you will only receive partial score.

```Input:
N = 3
Arr[][] = {{1,  2,  3}
           {4,  5,  6}
           {7,  8,  9}}
Output:
 3  6  9 
 2  5  8 
 1  4  7

```

CODE
```
void swap(int& a,int& b)
	{
	    int temp=a;
	    a=b;
	    b=temp;
	}
	void rotateMatrix(vector<vector<int>>& arr, int n)
 {
	    // code here 
	    int i=0;
	    int j;
	    while(i<n)
	    {
	        j=0;
	        while(j<n-i-1)
	        {
	            swap(arr[i][j],arr[n-j-1][n-i-1]);
	            j++;
	        }
	        i++;
	    }
	    for(int i=0;i<n;i++)
	    {
	        reverse(arr[i].begin(),arr[i].end());
	    }
	}
```

** DESCRIPTION ** 
pepcoding channel rotate 2d array in clockwise direction 

TRICK here is first you need to transpose the array then you need to reverse each row after that the array will be rotated by 90 degree

refer to the images for better uderstanding 
else go for pepcoding video

![1686929900482](https://github.com/Chaithra007/Practice-/assets/107351787/d628e7e9-882c-40cf-80fd-4a318daf60fa)
![1686929900551](https://github.com/Chaithra007/Practice-/assets/107351787/f951f004-d9ce-481c-991f-16ffe659ef97)
![1686929900526](https://github.com/Chaithra007/Practice-/assets/107351787/5695e758-3ff6-490a-a350-b6f962602131)

