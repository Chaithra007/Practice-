PROBLEM STATEMENT 

Given an integer array nums, return the number of subarrays filled with 0.

A subarray is a contiguous non-empty sequence of elements within an array.

BRUTE FORCE CODE
```
long long zeroFilledSubarray(vector<int>& nums) {
        long long count=0;
        int n=nums.size();
        for(int i=0;i<n;i++)
        {
            for(int j=i;j<n;j++)
            {
                vector<int> temp;
                int val=0;
                for(int k=i;k<=j;k++)
                {
                    if(nums[k]==0)
                    {
                        val++;
                    }
                    temp.push_back(nums[k]);
                }
                if(temp.size()==val)
                {
                    count++;
                }
            }
        }
        return count;
    }
```
 CODE
```
long long zeroFilledSubarray(vector<int>& nums) {
        long long count=0;
        for(int i=0,j=0;i<nums.size();i++)
        {
            //if the subarray does not start with azero then move the j until you find a subarray that starts with zero 
            if(nums[i]!=0)
            {
                j=i+1;
            }
            //this is to count the length of the subarray
            count+=i-j+1;
        }
        return count;
    }
```

**DESCRIPTION**
when you make a subarray and push it into a vector just make sure that whenever you encouter a zero increment the count and check if the count is equal to the size of the subarray vector that just created . If it is equal increment the count value because that subarray only contains zero 
![1688318501091](https://github.com/Chaithra007/Practice-/assets/107351787/142bf99b-f370-49e1-b819-ff430b6ae68a)

