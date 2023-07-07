# LC-Python34
Dynamic planning 3


## 343.Integer Break, 96.Unique Binary Search Trees
July 06, 2023  4h

Congratulations!\
This is the 34th day for leetcode python study. Today we will learn about the Dynamic planning!\
The challenges today are hard and especially about finding the recursive formula for the dynamic planning. 


## 343.Integer Break
Here dp[i] means the largest result we can get for integer i. We can break i into 2 integers j and i-j. And we can also continue to break i-j into more integers, this will change i into sum of more than just 2 integers.
```python
class Solution:
    def integerBreak(self, n: int) -> int:
        dp = [0] * (n+1)
        dp[2] = 1

        for i in range(3, n+1):
            for j in range(1, i//2+1):      #the j is the cutting point
                dp[i] = max(dp[i], j*(i-j), j*dp[i-j])      #here we keep update dp[i] and get the max
        
        return dp[n]
```


## 96.Unique Binary Search Trees
```python
class Solution:
    def numTrees(self, n: int) -> int:
        dp = [0] * (n+1)        #starts from 0 to n
        dp[0] = 1       #a blank tree, still is 1
        for i in range(1, n+1):     #iterate from 1 to n
            for j in range(1, i+1):     #for each number i, calculate the number of binary search trees with j as the root 
                dp[i] += dp[j-1] * dp[i-j]      #the number of left subtrees times the number of right subtrees
        
        return dp[n]
```



