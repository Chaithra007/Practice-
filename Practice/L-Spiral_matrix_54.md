PROBLEM STATEMENT 

Given an m x n matrix, return all elements of the matrix in spiral order.

![image](https://github.com/Chaithra007/Practice-/assets/107351787/a5a5e7b4-72a6-4eb5-ac7a-c0c96f7105c4)

```
Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [1,2,3,6,9,8,7,4,5]
```
CODE
```
vector<int> spiralOrder(vector<vector<int>>& matrix) {
        int r=matrix.size();
        int c=matrix[0].size();
       vector<int> ans;
        int minr=0;
        int minc=0;
        int maxr=r-1;
        int maxc=c-1;
        int nele=r*c;
        int count=0;
        while(count<nele)
        {
            //top wall
            for(int i=minr,j=minc;j<=maxc && count<nele;j++)
            {
                ans.push_back(matrix[i][j]);
                count++;
            }
            minr++;
            //right wall
            for(int i=minr,j=maxc;i<=maxr && count<nele;i++)
            {
                ans.push_back(matrix[i][j]);
                count++;
            }
            maxc--;
            //bottom wall
            for(int j=maxc,i=maxr;j>=minc && count<nele;j--)
            {
                ans.push_back(matrix[i][j]);
                count++;
            }
            maxr--;
            //left wall
            for(int i=maxr,j=minc;i>=minr && count<nele;i--)
            {
                ans.push_back(matrix[i][j]);
                count++;
            }
            minc++;
        }
        return ans;
    }
```

** DESCRIPTION **

instead of considering the matrix as a spiral matrix you can consider it as a box and then traverse all the for walls and after you traverse all the walls decrement the value of the r and column on each corner and then when you reach the inner box continue the similar process until you process all the elements in the matrix

pepcoding video this problem is clockwise direction and the explanation is in anti-clockwise direction 

Refer to the below images for better explanation 


![1687023730650](https://github.com/Chaithra007/Practice-/assets/107351787/163522a6-d17b-4fe0-9790-29cd24034ad5)

![1687023730688](https://github.com/Chaithra007/Practice-/assets/107351787/7c5fb1e7-762d-4ef1-a793-3c412e0ed5c3)

![1687023730710](https://github.com/Chaithra007/Practice-/assets/107351787/4959ee71-c153-4cd3-a898-ccdefa88fe99)

