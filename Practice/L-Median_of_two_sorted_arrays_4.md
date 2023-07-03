PROBLEM STATEMENT 

Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

CODE
```
void merge(vector<int> & nums1,vector<int>& nums2,vector<int>& ans)
{
    int l=0;
    int j=0;
    int n1=nums1.size();
    int n2=nums2.size();
    while(l<n1 && j<n2)
    {
        if(nums1[l]<=nums2[j])
        {
            ans.push_back(nums1[l]);
            l++;
        }
        else
        {
            ans.push_back(nums2[j]);
            j++;
        }
    }
    while(l<n1)
    {
        ans.push_back(nums1[l]);
        l++;
    }
    while(j<n2)
    {
        ans.push_back(nums2[j]);
        j++;
    }
    
}
    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        vector<int> ans;
        merge(nums1,nums2,ans);
        double res=0;
        if((ans.size()%2)!=0)
        {
            int a=ans.size()/2;
            res=ans[a];
            return res;
        }
        int a=ans.size()/2;
        res=(ans[a]+ans[a-1])/2.0;
        return res;
    }
```

**DESCRIPTION **
Noting much but make use of merge and then merge the arrays in sorted order 

res=(ans[a]+ans[a-1])/2.0;

That last 2.0 is very important for the data to be converted into double format 


