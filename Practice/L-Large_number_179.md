PROBLEM STATEMENT

Given a list of non-negative integers nums, arrange them such that they form the largest number and return it.

Since the result may be very large, so you need to return a string instead of an integer.

CODE 
```
string largestNumber(vector<int>& nums)
{
        sort(nums.begin(),nums.end(),[&](const int& a,const int& b){
            string s1=to_string(a)+to_string(b);
            string s2=to_string(b)+to_string(a);
            return s1>s2;
        });
        string ans="";
        for(auto& c: nums)
        {
            ans+=to_string(c);
        }
        if(ans[0]=='0')
        {
            return "0";
        }
        return ans;
}
```
** Description**

Sort the array in such a way that when we compare the concatenated string of both the elements in the array in any 2 types the type must give us the largest of two types .
refer to the image below for better understanding and see neetcode video for even better understanding 


![1686466094524](https://github.com/Chaithra007/Practice-/assets/107351787/d01d6d52-4656-420d-b8dd-12432e82c144)
