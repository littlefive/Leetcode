# 旋转数组
> 给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。

示例 1:

输入: [1,2,3,4,5,6,7] 和 k = 3
输出: [5,6,7,1,2,3,4]
> pop(),shift()返回的是当前pop的项， unshift()，push()返回长度
``` javascript
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var rotate = function(nums, k) {
    k > nums.length && (k=k%nums.length);
    while(k>0){
        nums.unshift(nums.pop())
        k--
    }
};

```
> k > nums.length && (k=k%nums.length); 这一行当时考虑优化的点是，如果传入的k值大于数组长度，可以取余数，这样可以更优的旋转数组
