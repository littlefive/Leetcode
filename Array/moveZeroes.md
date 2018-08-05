# 移动零
> 把零移动到最后
给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

示例:

输入: [0,1,0,3,12]
输出: [1,3,12,0,0]
```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
    var len = nums.length;
    for(var i=0; i<len; i++){
        if(!nums[i]){
            nums.push(0);
            nums.splice(i, 1)
            i--;
            len--;
        }
    }
};
> 需要考虑操作过后的数组的长度，索引
```
