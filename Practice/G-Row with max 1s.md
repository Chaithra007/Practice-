
PROBLEM STATEMENTS

Given a boolean 2D array of n x m dimensions where each row is sorted. Find the 0-based index of the first row that has the maximum number of 1's.

![image](https://github.com/Chaithra007/Practice-/assets/107351787/d6f6549b-616a-49c0-b3f7-5fd2020b114c)


CODE
```
int rowWithMax1s(vector<vector<int> > arr, int n, int m) {
	    // code here
	    int ans=-1;
	    int i=0;
	    int j=m-1;
	    while(i<n && j>=0)
	    {
	        if(arr[i][j]==1)
	        {
	            ans=i;
	            j--;
	        }
	        else
	        {
	            i++;
	        }
	    }
	    return ans;
}
```
**DESCRIPTION **
if the matrix row are not sorted sort them first then just run a while loop and store the index and decrement j value whenever you encounter a 1 value 

