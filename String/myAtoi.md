# 字符串转整数
假设我们的环境只能存储 32 位有符号整数，其数值范围是 [−231,  231 − 1]。如果数值超过可表示的范围，则返回  INT_MAX (231 − 1) 或 INT_MIN (−231) 。

示例 1:

输入: "42"
输出: 42
示例 2:

输入: "   -42"
输出: -42
解释: 第一个非空白字符为 '-', 它是一个负号。
     我们尽可能将负号与后面所有连续出现的数字组合起来，最后得到 -42 。
示例 3:

输入: "4193 with words"
输出: 4193
解释: 转换截止于数字 '3' ，因为它的下一个字符不为数字。
示例 4:

输入: "words and 987"
输出: 0
解释: 第一个非空字符是 'w', 但它不是数字或正、负号。
     因此无法执行有效的转换。
```javascript
/**
 * @param {string} str
 * @return {number}
 */
var myAtoi = function(str) {
    let num = Number.parseInt(str, 10);
    let max = Math.pow(2, 31);
    
    if (!num) {
        num = 0;
    }
    if(num > 0){
        num = num >= max ? max-1 : num;
    } else {
        num = num <= -max ? -max : num;
    }
    return num
    
};
```
