PROBLEM STATEMENT 

Given an input string (s) and a pattern (p), implement wildcard pattern matching with support for '?' and '*' where:

'?' Matches any single character.
'*' Matches any sequence of characters (including the empty sequence).
The matching should cover the entire input string (not partial).

CODE
```
class Solution {
public:
bool f(int i, int j, const string& s, const string& p)
{
    if (i < 0 && j < 0)
    {
        return true;
    }
    if (j < 0)
    {
        for (int ii = 0; ii <= i; ii++)
        {
            if (p[ii] != '*')
                return false;
        }
        return true;
    }
    if (i < 0)
    {
        return false;
    }
    if (p[i] == s[j] || p[i] == '?')
        return f(i - 1, j - 1, s, p);
    if (p[i] == '*')
        return f(i - 1, j, s, p) || f(i, j - 1, s, p);
    return false;
}

bool isMatch(string str, string pattern)
{
    int n = str.size();
    int m = pattern.size();
    return f(m - 1, n - 1, str, pattern);
}


};

```

**DESCRIPTION**
This is a recursive solution yet to conver this to dynamic programming
refer to the images below for futher explanation 

![1686623366361](https://github.com/Chaithra007/Practice-/assets/107351787/6b778800-0528-4f8e-8100-df3a3041b96f)
![1686623366327](https://github.com/Chaithra007/Practice-/assets/107351787/b0cabf98-5b6e-45b7-96c2-424195d678dd)
![1686623366281](https://github.com/Chaithra007/Practice-/assets/107351787/d6c2d8f3-6c0e-43ae-ac64-8179bca4994c)


