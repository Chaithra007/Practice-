PROBLEM STATEMENT 

Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive.

There is only one repeated number in nums, return this repeated number.

You must solve the problem without modifying the array nums and uses only constant extra space.

EXAMPLE 

```
Input: nums = [1,3,4,2,2]
Output: 2
```

CODE
```
int findDuplicate(vector<int>& nums) {
        unordered_map<int,int> map;
        int n=nums.size();
        for(int i=0;i<n;i++)
        {
            map[nums[i]]++;
        }
        int ans=0;
        for(auto x:map)
        {
            if(x.second>1)
            {
                ans=x.first;
                break;
            }
        }
        return ans;
    }
```

** DESCRIPTION**

Just make use of a hash map and print the key of the value that is grater than 1 
