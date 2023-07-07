# LC-Python34
Dynamic planning 3


## 343.Integer Break
July 06, 2023  4h

Congratulations!\
This is the 34th day for leetcode python study. Today we will learn about the Dynamic planning!\
The challenges today are hard and especially about ~~unique paths to a destination~~. 


## 343.Integer Break
Here dp[i] means the largest result we can get for interger i. We can break i into 2 intergers j and i-j. And we can also continue to break i-j into more integers, this will change i into sum of more than just 2 intergers.
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



## 96.
不同的二叉搜索树 




