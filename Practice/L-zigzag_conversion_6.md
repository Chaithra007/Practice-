PROBLEM STATEMENT 

The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)
```
P   A   H   N
A P L S I I G
Y   I   R
```
And then read line by line: "PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:

```
string convert(string s, int numRows);
```

CODE
```
 string convert(string s, int numRows) {
        if(numRows==1)
        {
            return s;
        }
        string ans="";
        int increment=0;
        int i=0;
        while(i<numRows)
        {
            increment=2*(numRows-1);
            for(int j=i;j<s.size();j+=increment)
            {
                ans+=s[j];
                if(i>0 && i<numRows-1 && j+increment-2*i<s.size())
                {
                    ans+=s[j+increment-2*i];
                }
            }
            i++;

        }
        return ans;
    }
 ```
 
 **DESCRIPTION**
 
 if the number of rows in 1 then return the entire string 
else
you need to iterate to all the rows each time and each time you iterate a row within the row increment is 2*(numRows-1) and 
for each V there will one more extra character except for the first and last row 
for that extra character in the V we have a if check within the row iteration 
the row j+increment-2*i<s.size()

Refer to the images below for better explanation of last few statements 
![1686668884615](https://github.com/Chaithra007/Practice-/assets/107351787/0e482a33-2094-4c31-8080-c6348131d848)
![1686668884718](https://github.com/Chaithra007/Practice-/assets/107351787/1c8781c2-bd5f-4088-8e88-967971175513)
