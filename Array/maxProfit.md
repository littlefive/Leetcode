# 买卖股票的最佳时机 II
> 输入: [7,1,5,3,6,4]
输出: 7
解释: 在第 2 天（股票价格 = 1）的时候买入，在第 3 天（股票价格 = 5）的时候卖出, 这笔交易所能获得利润 = 5-1 = 4 。
     随后，在第 4 天（股票价格 = 3）的时候买入，在第 5 天（股票价格 = 6）的时候卖出, 这笔交易所能获得利润 = 6-3 = 3 。
    
``` javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
    var sum=0;
    var len = prices.length;
  for(var i=0; i<len;i++){
      var num = prices[i+1]-prices[i];
       num > 0  && (sum+=num)
  }  
    return sum
};
```
> 这个其实是个贪心算法，局部最优加到一块就属于最优方案
