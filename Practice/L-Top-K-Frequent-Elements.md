PROBLEM STATEMENT 

Given an integer array nums and an integer k, return the k most frequent elements. You may return the answer in any order.

CODE
```
vector<int> topKFrequent(vector<int>& nums, int k) {
unordered_map<int,int> map;
        vector<int> ans;
        for(int i=0;i<nums.size();i++)
        {
            map[nums[i]]++;
        }
        priority_queue<int> qu;
        for(auto x:map)
        {
            qu.push(x.second);
        }
        while(k>0 && !qu.empty())
        {
            k--;
            int ele=qu.top();
            for(auto x:map)
            {
                if(x.second==ele)
                {
                    ans.push_back(x.first);
                    map.erase(x.first);
                    break;
                }
            
            } 
            qu.pop();
        }
        return ans;
    }
```
**DESCRIPTION**
Make use of hash map and priority queues to solve this question 
