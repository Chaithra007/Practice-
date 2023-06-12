PROBLEM STATEMENT 

The complement of an integer is the integer you get when you flip all the 0's to 1's and all the 1's to 0's in its binary representation.

For example, The integer 5 is "101" in binary and its complement is "010" which is the integer 2.
Given an integer num, return its complement.

CODE
```
int findComplement(int n) {
        vector<int> v;
        while(n!=0)
        {
            v.push_back(n%2);
            n=n/2;
        }
        reverse(v.begin(),v.end());
        for(int i=0;i<v.size();i++)
        {
            if(v[i]==1)
            {
                v[i]=0;
            }
            else
            {
                v[i]=1;
            }
        }
        long long two=1;
        for(int i=v.size()-1;i>=0;i--)
        {
            n=n+v[i]*two;
            two=two*2;
        }
        return n;
    }
```

**DESCRIPTION**
first convert the number to its binary representation (while loop) 
reverse the binary rep because the binary digits were pushed at the end
next convert all ones to zero 
convert the binary representation back to number
    
