PROBLEM STATEMENT

Given a string s, return the longest palindromic substring in s.


```
string longestPalindrome(string str) {
        int i=0;
        int resl=0;
        int resr=0;
        int reslen=0;
        string ans;
        int l,r;
        for(i=0;i<str.size();i++)
        {
            //odd length
            l=i;
            r=i;
            while(l>=0 && r<str.size() && str[l]==str[r])
            {
                if((r-l+1)>=reslen)
                {
                    resl=l;
                    resr=r;
                    reslen=r-l+1;
                }
                l--;
                r++;
            }
              l=i;
              r=i+1;
            while(l>=0 && r<str.size() && str[l]==str[r])
            {
                if((r-l+1)>reslen)
                {
                    resl=l;
                    resr=r;
                    reslen=r-l+1;
                }
                l--;
                r++;
            }
           
        }
        
       while(resl<=resr)
       {
           ans+=str[resl];
           resl++;
       }
        return ans;
}   
```

**DESCRIPTION**
for loop to traverse the array 
now for each character you need to check for left and right character then if they are equal we will expand the window size for the pallindrome(while loops )
This will vary for odd and even length palindrome if the palindrome is of even length then r=i+1 and then continue the same process as we did for odd length
and one more thing expand the only of the window is greater than the reslen(longest window till now.

If “aba” is a palindrome, is “xabax” a palindrome? Similarly is “xabay” a palindrome ------------------->Here you go the basic funda
