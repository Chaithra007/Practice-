PROLEM STATEMENT 

You are given an integer array deck. There is a deck of cards where every card has a unique integer. The integer on the ith card is deck[i].

You can order the deck in any order you want. Initially, all the cards start face down (unrevealed) in one deck.

You will do the following steps repeatedly until all cards are revealed:

Take the top card of the deck, reveal it, and take it out of the deck.
If there are still cards in the deck then put the next top card of the deck at the bottom of the deck.
If there are still unrevealed cards, go back to step 1. Otherwise, stop.
Return an ordering of the deck that would reveal the cards in increasing order.

Note that the first entry in the answer is considered to be the top of the deck.

 ```
Input: deck = [17,13,11,2,3,5,7]
Output: [2,13,3,11,5,17,7]
Explanation: 
We get the deck in the order [17,13,11,2,3,5,7] (this order does not matter), and reorder it.
After reordering, the deck starts as [2,13,3,11,5,17,7], where 2 is the top of the deck.
We reveal 2, and move 13 to the bottom.  The deck is now [3,11,5,17,7,13].
We reveal 3, and move 11 to the bottom.  The deck is now [5,17,7,13,11].
We reveal 5, and move 17 to the bottom.  The deck is now [7,13,11,17].
We reveal 7, and move 13 to the bottom.  The deck is now [11,17,13].
We reveal 11, and move 17 to the bottom.  The deck is now [13,17].
We reveal 13, and move 17 to the bottom.  The deck is now [17].
We reveal 17.
Since all the cards revealed are in increasing order, the answer is correct.
```

In this question you can learn the usage of queues 

CODE
```
vector<int> deckRevealedIncreasing(vector<int>& deck) {
        queue<int> q;
        vector<int> res(deck.size());
        sort(deck.begin(),deck.end());

        for(int i=0;i<deck.size();i++)
        {
            q.push(i);
        }

        int j=0;
        while(!q.empty())
        {
            int ind=q.front();
            res[ind]=deck[j++];
            q.pop();
            if(q.size()>1)
            {
                int k=q.front();
                q.pop();
                q.push(k);
            }
        }
        return res;
    }

```

** DESCRIPTION **

see leetcode solution for better understanding 

to understand the code you need to dry run it 
first sort the array 
then maintain a queue that has all the indexes 
make a resultant array that is equivalent to the size of the array 
keep updating the size of the array 
now just keep adding the elements to the appropriate index 

Refer the below images for beter explanation 

![1689102381064](https://github.com/Chaithra007/Practice-/assets/107351787/8bed7dae-a4ec-414f-a668-0246c47bd2ad)
