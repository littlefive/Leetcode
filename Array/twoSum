# 两数之和
给定一个整数数组和一个目标值，找出数组中和为目标值的两个数。

你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。

示例:

给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    var number=[];
    for(var i=0;i<nums.length;i++){
        
            let cur = nums[i];
            var yu = target - nums[i];
            nums.splice(i, 1);
            var index = nums.indexOf(yu);
            nums.splice(i, 0, cur)
            if(index != -1){
                number = number.concat(i, index+1)
                break
            }
        }
    
    return number
};
```
