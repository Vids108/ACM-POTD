                                                          Best Time to Buy and Sell Stock
You are given an integer array prices where prices[i] represents the stock price on the i-th day. The goal is to maximize profit by choosing one day to buy and a
later day to sell the stock. If no profit is possible, return 0. An efficient solution uses a greedy approach. While traversing the array, track the minimum price
seen so far as the best buying point. For each day, calculate the potential profit by subtracting this minimum price from the current price and update
the maximum profit if it is larger. This approach ensures O(n) time complexity and constant O(1) space.

CODE:

class Solution {
    public int maxProfit(int[] prices) {
        int minPrice = Integer.MAX_VALUE;
        int maxProfit = 0;

        for (int price : prices) {
            if (price < minPrice) {
                minPrice = price;
            } else {
                maxProfit = Math.max(maxProfit, price - minPrice);
            }
        }

        return maxProfit;
    }
}
