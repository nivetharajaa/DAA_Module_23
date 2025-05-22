# EX 5B Coin Change Problem
## DATE: 12.04.2025
## AIM:
To compute the fewest number of coins that we need to make up the amount given.
## Algorithm
1. If amount is 0, answer is 0; if coins are too big, answer is -1.
2. Make a list dp to remember the fewest coins needed for each amount.
3. Set 1 coin for amounts equal to the coin values.
4. For bigger amounts, check if using a coin gives fewer coins, and update.
5. At the end, return the answer from dp[amount]
## Program:
```
/*
Create a python function to compute the fewest number of coins that we need to make up the amount given.
Developed by: Nivetha A
Register Number: 212222230101 
*/
```
```
class Solution(object):
   def coinChange(self, coins, amount):
        dp = [float('inf')] * (amount + 1)
        dp[0]=0
        for coin in coins:
            for i in range(coin, amount + 1):
                dp[i] = min(dp[i], dp[i - coin] + 1)
        return dp[amount] if dp[amount]!=float('inf') else -1
      
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))


print(ob1.coinChange(s,amt))
```
## Output:
![image](https://github.com/user-attachments/assets/f69b3af4-c72b-4f42-b6e4-9f2c20e6637e)

## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
