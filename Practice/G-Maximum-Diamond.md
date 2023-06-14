## POTD
PROBLEM STATEMENT 

There are N bags with diamonds in them. The i'th of these bags contains A[i] diamonds.

If you drop a bag with A[i] diamonds, it changes to A[i]/2 diamonds and you gain A[i] diamonds.

Dropping a bag takes 1 minute. Find the maximum number of diamonds that you can take if you are given K minutes.

![image](https://github.com/Chaithra007/Practice-/assets/107351787/b7400619-fe0c-4309-b436-4d22b0258dd5)

CODE
```
long long maxDiamonds(int arr[], int n, int k) {
        // code here
        //this code is to basically max heap
        //Max heap structure is such that max element is always at the top 
        long long sum = 0;
        
        priority_queue<int>pq;
        for(int i=0; i<n; i++)
        {
            pq.push(arr[i]);
        }
        
        while(k && !pq.empty())
        {
            k--;
            sum += pq.top();
            pq.push(pq.top()/2);
            pq.pop();
        }
        
        return sum;
    }
```

**DESCRIPTION**

Use Priority Queue to calculate the answer.

this code is to basically max heap

Max heap structure is such that max element is always at the top 

add the max element from the priortiy queue to the ans then find the /2 of the max element and push it to the back of the priority queue which would heaplify on itself and again the max element will be on the top of the priority queue



