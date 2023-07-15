PROBLEM STATEMENT 

Given a string s, sort it in decreasing order based on the frequency of the characters. The frequency of a character is the number of times it appears in the string.

Return the sorted string. If there are multiple answers, return any of them.

```
Input: s = "tree"
Output: "eert"
Explanation: 'e' appears twice while 'r' and 't' both appear once.
So 'e' must appear before both 'r' and 't'. Therefore "eetr" is also a valid answer.
```
CODE

```
string frequencySort(string s) {
    unordered_map<char,int> map;
    string ans="";
    int n=s.size();
    for(int i=0;i<n;i++)
    {
        map[s[i]]++;
    }
    priority_queue<int> que;
    for(auto x: map)
    {
        que.push(x.second);
    }
    while(!que.empty())
    {
        int a=que.top();
        que.pop();
        for(auto x: map)
        {
            if(x.second==a)
            {
                while(a!=0)
                {
                    ans+=x.first;
                    map[x.first]--;
                    a--;
                }
            }
        }
    }
    return ans;
}
```

** DESCRIPTION **

hash map to store the count of all the characters in the string s

maintain a priority queue so that you can get the max count of elements at the top 

go into a while loop removing all the top elements from the queue and then finding the element in the map add the kep of the element to the answer until the count element becomes zero 
