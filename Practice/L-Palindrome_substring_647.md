PROBLEM STATEMENT 

Given a string s, return the number of palindromic substrings in it.

A string is a palindrome when it reads the same backward as forward.

A substring is a contiguous sequence of characters within the string.

```
int countSubstrings(string s) {
        int count=0;
        int l=0;
        int r=0;
        for(int i=0;i<s.length();i++)
        {
            l=i;
            r=i;
            while(l>=0 && r<s.length() && s[l]==s[r])
            {
                count++;
                l--;
                r++;
            }
            l=i;
            r=i+1;
            while(l>=0 && r<s.length() && s[l]==s[r])
            {
                count++;
                l--;
                r++;
            }
        }
        return count;
    }
```
**DESCRIPTION**
this question is very similar to the longest substring palindrome question 
Expanding window problem -window grows in both left and right side
//odd length palindrome 
l=i;
r=i;
//even length palindrome
l=i;
r=i+1;
refer to neetcode video for explanation and longest substring palindrome leetcode question 

   
