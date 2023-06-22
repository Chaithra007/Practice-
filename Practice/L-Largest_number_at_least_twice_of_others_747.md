PROBLEM STATEMENT 

You are given an integer array nums where the largest integer is unique.

Determine whether the largest element in the array is at least twice as much as every other number in the array. If it is, return the index of the largest element, or return -1 otherwise.

CODE
```
int dominantIndex(vector<int>& nums) {
        int ans=-1; 
        int ma=*max_element(nums.begin(),nums.end());
        for(int i=0;i<nums.size();i++)
        {
            if(ma==nums[i])
            {
                ans=i;
            }
            else if(ma<2*nums[i])
            {
                return -1;
            }
        }
        return ans;
    }
```
