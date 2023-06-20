PROBLEM STATEMENT 
Given a string arr consisting of lowercase english letters, arrange all its letters in lexicographical order using Counting Sort.

CODE
```
 #define RANGE 255
    public:
    //Function to arrange all letters of a string in lexicographical 
    //order using Counting Sort.
    string countSort(string arr){
        // code here
        char output[arr.length()];
        int count[RANGE+1];
        memset(count,0,sizeof(count));
        for(int i=0;i<arr.length();i++)
        {
            count[arr[i]]++;
        }
        //prefix sum
        for(int i=1;i<RANGE;i++)
        {
            count[i]=count[i]+count[i-1];
        }
        for(int i=0;i<arr.length();i++)
        {
            output[count[arr[i]]-1]=arr[i];
            --count[arr[i]];
        }
        
       for(int i=0;arr[i];i++)
       {
           arr[i]=output[i];
       }
       return arr;
    }
```
** Description ** 
Refer to the images below 

![1687284809491](https://github.com/Chaithra007/Practice-/assets/107351787/e7495c22-9dcf-4ca4-89e0-9f7a20293937)
![1687284809541](https://github.com/Chaithra007/Practice-/assets/107351787/25373b37-7391-4e2e-b298-22518a3da5d7)
![1687284809574](https://github.com/Chaithra007/Practice-/assets/107351787/21ca25e5-b62d-49b8-a562-3382da373ac9)
