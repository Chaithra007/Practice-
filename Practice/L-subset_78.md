PROBLEM STATEMENT 

Given an integer array nums of unique elements, return all possible 
subsets
 (the power set).

The solution set must not contain duplicate subsets. Return the solution in any order.

LUV CODE
 ```
oid findsubset(int ind,vector<vector<int>>& ans,vector<int>& ds,vector<int>& nums)
    {
        if(ind==nums.size())
        {
            ans.push_back(ds);
            return;
        }
        findsubset(ind+1,ans,ds,nums);
        ds.push_back(nums[ind]);
        findsubset(ind+1,ans,ds,nums);
        ds.pop_back();
        
    }
```
STRIVER BETTER CODE

```
void findsubset(int ind,vector<vector<int>>& ans,vector<int>& ds,vector<int>& nums)
    {
        ans.push_back(ds);
        for(int j=ind;j<nums.size();j++)
        {
            ds.push_back(nums[j]);
            findsubset(j+1,ans,ds,nums);
            ds.pop_back();
        }
        
    }
```
HAVE A LOOK AT THE WRONG METHOD FOLLOWED IN THE BELOW CODE

```
vector<vector<int>> subsets(vector<int>& nums) {
        /*sort(nums.begin(),nums.end());
        vector<vector<int>> ans;
        vector<int> ds1;
        ans.push_back(ds1);
        for(int i=0;i<nums.size();i++)
        {
            for(int j=i;j<nums.size();j++)
            {
                vector<int> ds;
                for(int k=i;k<=j;k++)
                {
                    ds.push_back(nums[k]);
                }
                ans.push_back(ds);
                if(nums[i]!=nums[j])
                {
                    vector<int> a;
                    a.push_back(nums[i]);
                    a.push_back(nums[j]);
                    ans.push_back(a);
                }
                
            }
        }
        sort(ans.begin(),ans.end());
        ans.erase(unique(ans.begin(),ans.end()),ans.end());

        return ans;*/

```

** DESCRIPTION **

 Recursion - take and not take an element 

 refer to luv video 

 also have a look at striver subset sum 2 video for better explanation 

 

 ![1688889290623](https://github.com/Chaithra007/Practice-/assets/107351787/212551f0-b42e-4bb9-b346-9f8288b0675e)
