# 字符串中的第一个唯一字符
给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。

案例:

s = "leetcode"
返回 0.

s = "loveleetcode",
返回 2.

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var firstUniqChar = function(s) {
    // 初始值的设置，减少不必要的判断
    let num = -1;
    // 增加标识，不用去查询重复项
    let obj = {};
    for(var i=0;i<s.length;i++){
        if(obj[s[i]]) {
            continue
        }
        if(s.indexOf(s[i], i+1)===-1){
            num = i;
            break;
        } else {
            obj[s[i]] = 1;
        }
        
    }
    return num
};
```
