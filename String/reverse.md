# 颠倒整数
给定一个 32 位有符号整数，将整数中的数字进行反转。
```javascript
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
    let num = +(Math.abs(x).toString().split('').reverse().join('')) > Math.pow(2, 31) ? 0 : +(Math.abs(x).toString().split('').reverse().join(''));
    if(x>0){
        return num
    } else {
        return -num
    }
};
```
> math.abs()取的是绝对值， math.pow(2， 31)表示2的31次方
