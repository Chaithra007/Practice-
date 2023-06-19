
PROBLEM STATEMENT 

Given an m x n grid of characters board and a string word, return true if word exists in the grid.

The word can be constructed from letters of sequentially adjacent cells, where adjacent cells are horizontally or vertically neighboring. The same letter cell may not be used more than once.

![image](https://github.com/Chaithra007/Practice-/assets/107351787/b8369805-6a3c-48f1-92d2-4ad371eeac6f)

```
Input: board = [["A","B","C","E"],["S","F","C","S"],["A","D","E","E"]], word = "ABCCED"
Output: true
```

CODE
```
class Solution {
int dx[4]={1,0,-1,0};
int dy[4]={0,1,0,-1};
bool backtrack(int i,int j,vector<vector<char>>& board,string word,int ind)
{
    int row=board.size();
    int col=board[0].size();
    if(word.size()==ind)
    {
        return true;
    }
    if(i<0 || i>=row || j<0 || j>=col ||board[i][j]!=word[ind])
        return false;
    char t=board[i][j];
    board[i][j]='#';
    for(int k=0;k<4;k++)
    {
        if(backtrack(i+dx[k],j+dy[k],board,word,ind+1))
        {
            return true;
        }
    }
    board[i][j]=t;
    return false;
}

public:

    bool exist(vector<vector<char>>& board, string word) {
        int n=board.size();
        int m=board[0].size();
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<m;j++)
            {
                if(backtrack(i,j,board,word,0))
                {
                    return true;
                }
            }
        }
        return false;
    }
};
```

**DESCRIPTION **
Backtracking and dfs concepts 
