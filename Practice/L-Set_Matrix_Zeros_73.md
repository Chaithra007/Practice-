PROBLEM STATEMENT 

Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's.

You must do it in place.

![image](https://github.com/Chaithra007/Practice-/assets/107351787/8fd3944d-a31a-4b49-99c3-db51bf113d83)

```
Input: matrix = [[1,1,1],[1,0,1],[1,1,1]]
Output: [[1,0,1],[0,0,0],[1,0,1]]
```

CODE
```
void setZeroes(vector<vector<int>>& matrix) {
        unordered_map<int,int> acol;
        unordered_map<int,int> arow;
        int n=matrix.size();
        int m=matrix[0].size();
        for(int i=0;i<n;i++)
        {
            arow[i]=0;
        }
        for(int i=0;i<m;i++)
        {
            acol[i]=0;
        }
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<m;j++)
            {
                if(matrix[i][j]==0)
                {
                    arow[i]=1;
                    acol[j]=1;
                }
            }
        }
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<m;j++)
            {
                if(arow[i]==1 ||acol[j]==1)
                {
                    matrix[i][j]=0;
                }
            }
        }
        
    }
```

**DESCRIPTION**

You need to consider two more arrays - one of the size of a column and the other of the size of row 

initilaize both the arrays with a zero 

Next when you traverse the matrix make the both the array at a particular index zero when the cell has zero in it .

next if either of the columns or row array is 1 then mark that partcular cell as zero 

![1687108417681](https://github.com/Chaithra007/Practice-/assets/107351787/e3140275-5079-4527-8893-623f0aea103b)
![1687108417731](https://github.com/Chaithra007/Practice-/assets/107351787/8b56f2ec-67f4-44fa-b2cf-fa152c8b7d2e)

