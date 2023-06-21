PROBLEM STATEMENT 

Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.

```
Input: nums = [3,2,3]
Output: [3]
```

CODE
```
vector<int> majorityElement(vector<int>& nums) {
        vector<int> ans;
        int val=floor(nums.size()/3);
        unordered_map<int,int> map;
        for(int i=0;i<nums.size();i++)
        {
            map[nums[i]]++;
        }
        
        for(auto x:map)
        {
            if(x.second>val)
            {
                ans.push_back(x.first);
            }
        }
        return ans;
    }
```

**Description **

make use of a hashmap to store the count of all the values  in the array then traverse through the map to find the elements and push it into the array that has count value >n/3;

See Moore's Voting Algorithm

![1687359626415](https://github.com/Chaithra007/Practice-/assets/107351787/8d27d294-84ce-4f42-9cea-12f29b99e83d)
