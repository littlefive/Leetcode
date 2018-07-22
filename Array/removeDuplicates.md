# 从排序数组中删除重复项
> 给定 nums = [0,0,1,1,1,2,2,3,3,4],

函数应该返回新的长度 5, 并且原数组 nums 的前五个元素被修改为 0, 1, 2, 3, 4。

你不需要考虑数组中超出新长度后面的元素。 o(n)考虑时间线性复杂度
#### 方法一
> 16.9% 双重循环不建议，所以我写了方法二
``` javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var removeDuplicates = function(nums) {
    for(var i=0;i<nums.length;i++){
        for(var m=i+1; m<nums.length;m++) {
            if(nums[i]==nums[m]){
                nums.splice(m, 1);
                m--;
            }
        }
    }
    return nums.length
};
```
#### 方法二
> es6的set方法  71.2%
``` javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var removeDuplicates = function(nums) {
    var a = Array.from(new Set(nums));
     nums.length = 0;
    a.forEach(function(item){
        nums.push(item)
    })
};
```
