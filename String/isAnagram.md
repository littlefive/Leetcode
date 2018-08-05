# 有效的字母异位词

给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的一个字母异位词。

示例 1:

输入: s = "anagram", t = "nagaram"
输出: true
示例 2:

输入: s = "rat", t = "car"
输出: false
> 方法一
```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isAnagram = function(s, t) {
   return s.split('').sort().join('') === t.split('').sort().join('')

};
```
```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isAnagram = function(s, t) {
    let res;
    if(t===s) {
        return true
    }
    if(t.length !== s.length) {
        return false
    }
  for(var i=0; i<t.length; i++){
      if(s.indexOf(t[i]) === -1) {
          res = false;
          break;
      } else {
        s = s.replace(t.substr(i, 1), '');
          res = true;
      }
  }
    return res
};
```
