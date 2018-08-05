# 加一
给定一个非负整数组成的非空数组，在该数的基础上加一，返回一个新的数组。

最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。

你可以假设除了整数 0 之外，这个整数不会以零开头。
```javascript
/**
 * @param {number[]} digits
 * @return {number[]}
 */
var plusOne = function(digits) {
    for(var i=digits.length-1; i>=0; i--) {
        if(digits[i] === 9) {
                digits[i] = 0;
            if(i===0){
                digits.unshift(1);
                break
            }
        } else {
            digits[i]=digits[i]+1;
            break
        }
    }
    return digits
};
```
> 这个主要考虑的是最后一位是不是9，如果是9，就把当前位置置为0；还需要判断当前的9是不是在个位数，如果是，需要进位1；否则就在正常位+1
