------------------------------------------------------
Week 7: DP Tabulation
------------------------------------------------------
Day 43: Tabulation basics (convert memoized solutions)
Day 44: House robber (LC #198, #213)
Day 45: Longest increasing subsequence (LC #300)
Day 46: Knapsack (basic 0/1)
Day 47: Edit distance (LC #72)
Day 48: Review tabulation patterns
Day 49: Practice 3-4 medium DP problems

"""
Day 43: Tabulation Basics (Convert Memoized Solutions)
Author: [Your Name]
Date: [Today's Date]

Problems Covered:
1. LC #509 – Fibonacci Number
2. LC #70 – Climbing Stairs
"""

# ----------------------------------------------------
# 1. Fibonacci with Tabulation
# ----------------------------------------------------
"""
Memoized (Top-Down) version:
    fib(n) = fib(n-1) + fib(n-2)

Tabulation (Bottom-Up) approach:
    - Create dp array where dp[i] = Fibonacci(i)
    - Fill from base cases upwards
    - Time: O(n), Space: O(n) (can be reduced to O(1))
"""

def fib_tab(n):
    if n <= 1:
        return n
    
    dp = [0] * (n + 1)
    dp[0], dp[1] = 0, 1
    
    for i in range(2, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]
    
    return dp[n]


# ----------------------------------------------------
# 2. Climbing Stairs with Tabulation (LC #70)
# ----------------------------------------------------
"""
Memoized version:
    ways(n) = ways(n-1) + ways(n-2)

Tabulation approach:
    - dp[i] = number of ways to reach step i
    - Base cases: dp[1] = 1, dp[2] = 2
"""

def climbStairs_tab(n):
    if n <= 2:
        return n
    
    dp = [0] * (n + 1)
    dp[1], dp[2] = 1, 2
    
    for i in range(3, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]
    
    return dp[n]


# ----------------------------------------------------
# Example Usage
# ----------------------------------------------------
if __name__ == "__main__":
    # Fibonacci
    print("Fibonacci(10):", fib_tab(10))  # Expected: 55
    
    # Climbing Stairs
    print("Climbing Stairs (n=5):", climbStairs_tab(5))  # Expected: 8


# ----------------------------------------------------
# Key Notes:
# ----------------------------------------------------
# - Tabulation builds the solution iteratively (Bottom-Up).
# - Usually more space-efficient than memoization.
# - Common trick: replace dp array with 2 variables.
# ----------------------------------------------------
