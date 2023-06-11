PROBLEM STATEMENT 

Given two strings s and t of lengths m and n respectively, return the minimum window substring of s such that every character in t (including duplicates) is included in the window. If there is no such substring, return the empty string "".

The testcases will be generated such that the answer is unique.

CODE
```
string minWindow(string s, string p) {
        unordered_map<char, int> map1;
        for (char c : p) {
            map1[c]++;
        }
        
        int i = 0;
        int j = 0;
        int matchcount = 0;
        int dmt = p.size();
        int minLen = INT_MAX;
        int startIdx = -1;
        unordered_map<char, int> map2;
        
        while (j < s.length()) 
        {
            if (map1.find(s[j]) != map1.end()) {
                map2[s[j]]++;
                if (map2[s[j]] <= map1[s[j]]) {
                    matchcount++;
                }
            }
            
            while (matchcount == dmt) {
                int currLen = j - i + 1;
                if (currLen < minLen) {
                    minLen = currLen;
                    startIdx = i;
                }
                
                if (map1.find(s[i]) != map1.end()) {
                    map2[s[i]]--;
                    if (map2[s[i]] < map1[s[i]]) {
                        matchcount--;
                    }
                }
                
                i++;
            }
            
            j++;
        }
        
        if (startIdx == -1) {
            return "";
        }
        
        return s.substr(startIdx, minLen);
    }
 ```
 
 **DESCRIPTION **
 
    First maintain a frequency map for the string for which you need to find a substring 
There are basically 3 fundas in this question that needs to be followed 
1) Acquire - increase the size of the window until you make the match count variable to be equal to the size of the string p 
   match count will increase only if the letter found in the string p is found in the string s 
   
2 ) Release decrease the size of the window matchcount<p.size()
once the matchcount becomes less than p.size() you again start to increase the size of the window 

Repeat this acquire-match-release-until match <p.size() until j reaches the end of the actual string 
i and the j are the pointers used to increase or decrease the size of the window 
j to acquire 
i to release 

Refer to the images below 
![1686507488305](https://github.com/Chaithra007/Practice-/assets/107351787/f3eb9811-e03d-468c-9d5f-01565a11b198)
![1686507488265](https://github.com/Chaithra007/Practice-/assets/107351787/6866039e-a8f4-4e0b-af35-010a5001f04d)
![1686507488199](https://github.com/Chaithra007/Practice-/assets/107351787/d1ae4a7b-ecbb-46f0-883b-ffe564834724)

  
