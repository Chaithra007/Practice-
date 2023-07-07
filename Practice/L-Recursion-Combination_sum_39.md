PROBLEM STATEMENT 

Given an array of distinct integers candidates and a target integer target, return a list of all unique combinations of candidates where the chosen numbers sum to target. You may return the combinations in any order.

The same number may be chosen from candidates an unlimited number of times. Two combinations are unique if the 
frequency
 of at least one of the chosen numbers is different.

The test cases are generated such that the number of unique combinations that sum up to target is less than 150 combinations for the given input.

CODE
```
void combi(int ind,int target,vector<int>& candidates,vector<vector<int>>& ans,vector<int>& ds)
    {
        if(ind==candidates.size())
        {
            if(target==0)
            {
                ans.push_back(ds);
            }
            return;
        }
        

        if(candidates[ind]<=target)
        {
            //pick
            
            ds.push_back(candidates[ind]);
            combi(ind,target-candidates[ind],candidates,ans,ds);
            //it is very necessary to remove the element because we need to perform the not pick operation 
            ds.pop_back();
        }
        //not pick 
        combi(ind+1,target,candidates,ans,ds);
    }
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {
        vector<vector<int>> ans;
        vector<int> ds;
        combi(0,target,candidates,ans,ds);
        return ans;
    }
```
**DESCRIPTION **
Recursive problem 

pick and not pick 

![1688751544271](https://github.com/Chaithra007/Practice-/assets/107351787/a4fb2df9-a131-42d3-ba53-8ebe3f67435c)
![1688751544305](https://github.com/Chaithra007/Practice-/assets/107351787/92d07678-898e-45c3-b779-b5735175511c)


