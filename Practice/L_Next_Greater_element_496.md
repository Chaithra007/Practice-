PROBLEM STATEMENT 

The next greater element of some element x in an array is the first greater element that is to the right of x in the same array.

You are given two distinct 0-indexed integer arrays nums1 and nums2, where nums1 is a subset of nums2.

For each 0 <= i < nums1.length, find the index j such that nums1[i] == nums2[j] and determine the next greater element of nums2[j] in nums2. If there is no next greater element, then the answer for this query is -1.

Return an array ans of length nums1.length such that ans[i] is the next greater element as described above.

INPUT
```
Input: nums1 = [4,1,2], nums2 = [1,3,4,2]
Output: [-1,3,-1]
Explanation: The next greater element for each value of nums1 is as follows:
- 4 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.
- 1 is underlined in nums2 = [1,3,4,2]. The next greater element is 3.
- 2 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.
```
CODE
```
vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
        vector<int> ans;
        stack<int> st;
        unordered_map<int,int> map;
        for(int j=nums2.size()-1;j>=0;j--)
        {
            while(!st.empty() && nums2[j]>=st.top())
            {
                st.pop();
            }
            if(!st.empty())
            {
                map[nums2[j]]=st.top();
            }
            else
            {
                map[nums2[j]]=-1;
            }
            st.push(nums2[j]);
        }
        for(auto x:nums1)
        {
            if(map.find(x)!=map.end())
            {
                ans.push_back(map[x]);
            }
        }
        return ans;
    }
```
Whenver we want to check for the next greater element for a particluar element we need to check

if the top of the stack has an element that is grater than the current element if the element is greater than the currrent element then we push the top elemnt of the stack into the answer .

If the current element is greater than the top of the stack then we remove the top element from the stack until we find an element that is greater than the current element . 

At the end push the current element on to the stack 

Just watch striver video for better explanation 

![WhatsApp Image 2023-08-03 at 22 03 07](https://github.com/Chaithra007/Practice-/assets/107351787/c28cdd35-6698-43da-8c82-6ba50e8cb0af)
![WhatsApp Image 2023-08-03 at 22 03 26](https://github.com/Chaithra007/Practice-/assets/107351787/3dee007a-f3e8-409c-a340-f93b94512f1e)
![WhatsApp Image 2023-08-03 at 22 03 41](https://github.com/Chaithra007/Practice-/assets/107351787/ea398e57-7a36-4743-b6ae-0d00849f4c9f)




