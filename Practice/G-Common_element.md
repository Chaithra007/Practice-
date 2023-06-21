PROBLEM STATEMENT 

Given three arrays sorted in increasing order. Find the elements that are common in all three arrays.

Note: can you take care of the duplicates without using any additional Data Structure?

```
Input:
n1 = 6; A = {1, 5, 10, 20, 40, 80}
n2 = 5; B = {6, 7, 20, 80, 100}
n3 = 8; C = {3, 4, 15, 20, 30, 70, 80, 120}
Output: 20 80
Explanation: 20 and 80 are the only
common elements in A, B and C.
```

CODE
```
vector <int> commonElements (int A[], int B[], int C[], int n1, int n2, int n3)
        {
            //code here.
            vector<int> ans;
            int i=0,j=0,k=0;
            while(i<n1 && j<n2 && k<n3)
            {
                
                if(A[i]==B[j] && B[j]==C[k])
                {
                    if(count(ans.begin(),ans.end(),A[i])==0)
                    {
                        ans.push_back(A[i]);
                    }
                    
                    i++;j++;
                    k++;
                    continue;
                }
                int mi=min(A[i],B[j]);
                int ele=min(C[k],mi);
                
                if(ele==A[i])
                {
                    i++;
                }
                else if(ele==B[j])
                {
                    j++;
                }
                else
                {
                    k++;
                }
                
            }
            return ans;
        }
```

** Description**

Three pointer approach 
move the pointer in the array that has the least value continue this until the any one of the 3 array is fully traversed 

refer to the image below 

![1687360139069](https://github.com/Chaithra007/Practice-/assets/107351787/79ae9b5c-2985-42ae-97b8-3b71abb859ad)
