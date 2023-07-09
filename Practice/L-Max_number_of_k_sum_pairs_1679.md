PROBLEM STATEMENT 

You are given an integer array nums and an integer k.

In one operation, you can pick two numbers from the array whose sum equals k and remove them from the array.

Return the maximum number of operations you can perform on the array.

TWO POINTER APPROACH 

CODE
```
sort(nums.begin(),nums.end());
        int n=nums.size();
        int count=0;
        int l=0;
        int r=n-1;
        while(l<r)
        {
            if(nums[l]+nums[r]==k)
            {
                count++;
                l++;
                r--;
            }
            else if(nums[l]+nums[r]>k)
            {
                r--;
            }
            else
            {
                l++;
            }
        }
        return count;
```

See that hash map one 

this didn't work for the testcase 
```
Input: nums = [3,1,3,4,3], k = 6
Output: 1
Explanation: Starting with nums = [3,1,3,4,3]:
- Remove the first two 3's, then nums = [1,4,3]
There are no more pairs that sum up to 6, hence a total of 1 operation.
```

HASH TABLE CODE

```
/*unordered_map<int,int> map;
        for(int i=0;i<nums.size();i++)
        {
            map[nums[i]]++;
        }
        int i=0;
        int n=nums.size();
        int count=0;
        while(map.size()!=0 && i<=n/2)
        {
            for(auto x:map)
            {
                if(map.find(k-x.first)!=map.end())
                {
                    count++;
                    map[x.first]--;
                    map[k-x.first]--;
                    if(map[x.first]<=0)
                    {
                        map.erase(x.first);
                    }
                    if(map[k-x.first]<=0)
                    {
                        map.erase(k-x.first);
                       
                    }
                     break;
                    
                }
            }
            i++;
        }
        return count;
```

** DESCRIPTION **
 
 2 pointer approach 
 
 sort the array first then find all the pairs that has sum value equal to k 

 ![1688890795669](https://github.com/Chaithra007/Practice-/assets/107351787/66683825-a5e3-44cc-a92b-93cf25a856e6)

 
