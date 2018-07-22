# 给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。

你的算法应该具有线性时间复杂度。 你可以不使用额外空间来实现吗？

示例 1:

输入: [2,2,1]
输出: 1

``` javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var singleNumber = function(nums) {
    nums.sort(function(value1, value2){
        if (value1 < value2) {
        return 1;
        } else if (value1 > value2) {
        return -1;
        } else {
        return 0;
        }

    })
    for(var i=0; i<nums.length; i++){
      if(nums[i]-nums[i+1] != 0) {
          return nums[i]
          
      }  else {
          i++
      }
    }
};
```
