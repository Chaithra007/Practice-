You are given two strings of the same length s and t. In one step you can choose any character of t and replace it with another character.

Return the minimum number of steps to make t an anagram of s.

An Anagram of a string is a string that contains the same characters with a different (or the same) ordering.

```
Input: s = "bab", t = "aba"
Output: 1
Explanation: Replace the first 'a' in t with b, t = "bba" which is anagram of s.
```

CODE
Make use of hash map to solve this question 

```
int minSteps(string s, string t) {
        unordered_map<char,int> tana;
        int n=s.size();
        int m=t.size();
        for(int i=0;i<m;i++)
        {
            tana[t[i]]++;
        }
        for(int i=0;i<n;i++)
        {
            if(tana.find(s[i])!=tana.end())
            {
                tana[s[i]]--;
            }
        }
        int count=0;
        for(auto x: tana)
        {
           if(x.second>0)
           {
               count+=x.second;
           }
        }
        return count;
    }
```

** DESCRIPTION **

first find the count of all the characters present in string t 

then iterate over the string s and then if the character in the string is found in the hashmap then just reduct the count of the character in the hashmap

count all the positive values in the hashmap

![1689274304775](https://github.com/Chaithra007/Practice-/assets/107351787/c9bd522c-3e1c-4e7f-ad70-93e69337f540)
