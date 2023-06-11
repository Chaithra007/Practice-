Problem statement 

Given an array of strings strs, group the anagrams together. You can return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once. 

CODE

```
vector<vector<string>> groupAnagrams(vector<string>& strs) {
vector<vector<string>> out;
    unordered_map<string,vector<string>> ans;
    for(int i=0;i<strs.size();i++)
    {
        string res=strs[i];
        sort(res.begin(),res.end());
        ans[res].push_back(strs[i]);
    }
    for(auto x:ans )
    {
        out.push_back(x.second);
    }
    return out;
    }
  ```
  
  DESCRIPTION
  pepcoding video
hashmap of hashmap 
but this approach is slightly different 
start iterating through the array of strings 
for each string now first you need to keep the string in some other temporary string and then sort the characters in the temporary string after this just push the original string to the hashmap such that the key is the sorted string 
now when we encounter a string with the same hashkey value then we just push the original key to the hashmap 

