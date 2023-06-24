PROBLEM STATEMENT 

Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

EXAMPLE EXPLANATION SAYS ALL ABOUT THE APPROACH FOLLOWED
```
Input: nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]
```

CODE

Better solution

```
void rotate(vector<int>& nums, int k) {
        int i=0;
        int n=nums.size();
        while(i<k)
        {
            int val=nums[n-1];
            int temp;
            for(int j=n-1;j>=1;j--)
            {
                nums[j]=nums[j-1];
            }
            nums[0]=val;
            i++;
        }
    }

```
optimal solution but O(n) extra space 

```
void rotate(vector<int>& nums, int k) {
        vector<int> copy=nums;
        int n=nums.size();
        for(int i=0;i<n;i++)
        {
            nums[(i+k)%n]=copy[i];
        }
    }
```

** DESCRIPTION **
Rotate the array see the example for the approach followed in the better solution 

