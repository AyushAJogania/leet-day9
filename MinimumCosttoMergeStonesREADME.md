# leet-day9

# Minimum Cost to Merge Stones

Given a row of stones represented by a vector `stones`, where each element `stones[i]` represents the number of stones in the ith pile, and an integer `k` representing the number of consecutive piles to merge in each move, we need to find the minimum cost to merge all piles of stones into one pile. If it is impossible to merge all piles into one, we return -1.

## Example

Input: `stones = [3, 2, 4, 1], k = 2`

Output: 20

Explanation: We start with `[3, 2, 4, 1]`. We merge `[3, 2]` for a cost of 5, and we are left with `[5, 4, 1]`. We merge `[4, 1]` for a cost of 5, and we are left with `[5, 5]`. We merge `[5, 5]` for a cost of 10, and we are left with `[10]`. The total cost was 20, and this is the minimum possible.

## Approach

To solve this problem, we can use dynamic programming. We create a 2D DP table `dp`, where `dp[i][j]` represents the minimum cost to merge piles from index `i` to index `j`. We then iteratively fill the DP table based on the given constraints.

The main part of the solution is the dynamic programming loop that iterates over different lengths of subarrays (from `k` to `n`). For each subarray, we try all possible splits using another loop with step `k - 1`. The goal is to find the minimum cost by recursively calculating the cost for the left and right parts of the split.

Finally, the minimum cost to merge all piles is stored in `dp[0][n - 1]`, where `n` is the length of the `stones` array. If it is not possible to merge all piles into one, we return -1.

## Complexity Analysis

- Time Complexity: O(n^3) where n is the length of the `stones` array. The solution involves filling the DP table of size n x n, and each cell requires O(n) operations to compute.
- Space Complexity: O(n^2) for the DP table.

The provided C++ code implements the above approach and includes test cases to validate the correctness of the solution.
