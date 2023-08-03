You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.


 ```
Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.
```

CODE
```
ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        int carry=0;
        ListNode* dummy=new ListNode(0);
        ListNode* current=dummy;
        while(l1||l2||carry)
        {
            int sum=carry;
            if(l1)
            {
                sum+=l1->val;
                l1=l1->next;
            }
            if(l2)
            {
                sum+=l2->val;
                l2=l2->next;
            }
            carry=sum/10;
            sum=sum%10;
            current->next=new ListNode(sum);
            current=current->next;
        }
        return dummy->next;
    }
 ```

DESCRIPTION    

Initialize a dummy pointer to zero and make current point to it . 

consider a carry variable initalized to zero then whenever you find the sum of two corresponding numbers add the two numbers and along with carry 

next again perform a check to see if the generated number is a two digit number . if it is a two digit numeber then you need to find the carry by dividing the sum by 10 . 

Then you need to only consider the last digit (sum%10) and then add the last digit to the current by creating a linked list .
