PROBLEM STATEMENT 

Given a collection of candidate numbers (candidates) and a target number (target), find all unique combinations in candidates where the candidate numbers sum to target.

Each number in candidates may only be used once in the combination.

Note: The solution set must not contain duplicate combinations.

CODE
```
void combi(int ind,int target,vector<int> candidates,vector<vector<int>>& ans,vector<int> ds)
    {
        if(target==0)
        {
                ans.push_back(ds);
                return;
        }
        for(int i=ind;i<candidates.size();i++)
        {
            if(i>ind && candidates[i]==candidates[i-1])
                continue;
            if(candidates[i]>target)
                break;
            ds.push_back(candidates[i]);
            combi(i+1,target-candidates[i],candidates,ans,ds);
            ds.pop_back();
        }
        
        
    }
    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) {
        sort(candidates.begin(),candidates.end());
        vector<vector<int>> ans;
        vector<int> ds;
        combi(0,target,candidates,ans,ds);
        return ans;
```

** DESCRIPTION ** 

recursion striver

 refer the below images 

![1688888789563](https://github.com/Chaithra007/Practice-/assets/107351787/3c816c2c-ef97-484a-b889-9c22c920d853)
![1688888789672](https://github.com/Chaithra007/Practice-/assets/107351787/70cda5ba-98f9-4069-adea-eda0556f2390)
 ![1688888789732](https://github.com/Chaithra007/Practice-/assets/107351787/6e451cb0-c131-413e-a427-c0cf02a069c4)


