
# 两个数组的交集 II
给定两个数组，写一个方法来计算它们的交集。
例如:
给定 nums1 = [1, 2, 2, 1], nums2 = [2, 2], 返回 [2, 2].

```javascript
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
var intersect = function(nums1, nums2) {
    let arr = [];
    for(var i=0; i<nums1.length; i++) {
        if(nums2.indexOf(nums1[i])!=-1){
            arr.push(nums1[i]);
            nums2.splice(nums2.indexOf(nums1[i]), 1)
        }
    }
    return arr
};
```
