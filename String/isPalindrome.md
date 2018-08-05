# 验证回文字符串
给定一个字符串，验证它是否是回文串，只考虑字母和数字字符，可以忽略字母的大小写。

说明：本题中，我们将空字符串定义为有效的回文串。

示例 1:

输入: "A man, a plan, a canal: Panama"
输出: true
示例 2:

输入: "race a car"
输出: false
```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isPalindrome = function(s) {
    if(!s) {
        return true
    }
    var reg = /^[A-Za-z0-9]+$/;
    var j = s.length-1;
    var res = false;
    for(var i=0;i<s.length;i++){
        // 找到只剩中间的一个数了，就不用比较了，否则需要一直比较
        if(j-i<= 0) {
            res = true;
            break
        }
        if(!reg.test(s[i])){
            continue
        }
        if(!reg.test(s[j])) {
            j--; // 不是有效的数字或者字母，j需要找当前位置的前一位
            i--; // i是有效字符，还没有找到匹配的字符，所以当前位置-1，继续找，直到找到位置
            continue
        }
        if(s[i].toLowerCase() === s[j].toLowerCase()) {
            // 找到了，j就需要往前移动一位
            j--;
            res = true;
        } else {
            res = false
            break
        }
    }
    return res
};
```
